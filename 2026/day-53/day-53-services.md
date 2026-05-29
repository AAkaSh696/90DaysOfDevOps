# Day 53 – Kubernetes Services

## What Problem Services Solve

Pods in Kubernetes are temporary. If a Pod crashes or gets recreated, its IP address changes.

This creates a problem because applications cannot reliably communicate using changing Pod IPs.

Kubernetes Services solve this problem by providing:

* Stable IP addresses
* Stable DNS names
* Load balancing across Pods

Services sit in front of Pods and route traffic to healthy Pods automatically.

---

# Deployment Used

## app-deployment.yaml

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-app
  labels:
    app: web-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: web-app
  template:
    metadata:
      labels:
        app: web-app
    spec:
      containers:
      - name: nginx
        image: nginx:1.25
        ports:
        - containerPort: 80
```

This Deployment creates 3 Nginx Pods using the label:

```yaml
app: web-app
```

The Services use this label selector to route traffic to the Pods.

---

# ClusterIP Service

## clusterip-service.yaml

```yaml
apiVersion: v1
kind: Service
metadata:
  name: web-app-clusterip
spec:
  type: ClusterIP
  selector:
    app: web-app
  ports:
  - port: 80
    targetPort: 80
```

## Purpose

ClusterIP is the default Service type.

It allows communication only inside the Kubernetes cluster.

Traffic Flow:

```text
Pod → ClusterIP Service → Target Pods
```

I tested it using a temporary BusyBox pod and successfully accessed the Nginx page.

---

# NodePort Service

## nodeport-service.yaml

```yaml
apiVersion: v1
kind: Service
metadata:
  name: web-app-nodeport
spec:
  type: NodePort
  selector:
    app: web-app
  ports:
  - port: 80
    targetPort: 80
    nodePort: 30080
```

## Purpose

NodePort exposes the application outside the cluster using:

```text
<NodeIP>:<NodePort>
```

Example:

```text
http://localhost:30080
```

This is useful for:

* Development
* Testing
* Quick external access

---

# LoadBalancer Service

## loadbalancer-service.yaml

```yaml
apiVersion: v1
kind: Service
metadata:
  name: web-app-loadbalancer
spec:
  type: LoadBalancer
  selector:
    app: web-app
  ports:
  - port: 80
    targetPort: 80
```

## Purpose

LoadBalancer is mainly used in cloud environments like:

* AWS
* Azure
* GCP

It creates a cloud load balancer automatically and exposes the application publicly.

In my local cluster, the EXTERNAL-IP stayed:

```text
<pending>
```

because local Kubernetes clusters do not have a cloud provider integration.

---

# Difference Between Service Types

| Service Type | Accessible From        | Use Case               |
| ------------ | ---------------------- | ---------------------- |
| ClusterIP    | Inside cluster only    | Internal communication |
| NodePort     | Outside via Node IP    | Development & testing  |
| LoadBalancer | Public external access | Production             |

---

# Kubernetes DNS

Kubernetes automatically creates DNS entries for Services.

Format:

```text
<service-name>.<namespace>.svc.cluster.local
```

Example:

```text
web-app-clusterip.default.svc.cluster.local
```

I verified DNS resolution using:

```bash
nslookup web-app-clusterip
```

The returned IP matched the Service CLUSTER-IP.

---

# Endpoints

Endpoints are the actual Pod IPs behind a Service.

A Service routes traffic to these endpoints.

I checked them using:

```bash
kubectl get endpoints
```

This showed all Pod IPs connected to the Service.

---
<img width="1837" height="950" alt="Screenshot 2026-05-29 224958" src="https://github.com/user-attachments/assets/65c1b7ae-2b31-4b7c-9f0e-7a70969c6f3b" />
<img width="1506" height="645" alt="Screenshot 2026-05-29 225225" src="https://github.com/user-attachments/assets/942e787d-dfd2-44e1-8a7c-4973ea77d892" />
<img width="1288" height="579" alt="Screenshot 2026-05-29 225252" src="https://github.com/user-attachments/assets/44f7682c-70e4-444e-9417-fbb80c82a0cd" />
<img width="675" height="398" alt="Screenshot 2026-05-29 225311" src="https://github.com/user-attachments/assets/0b963b66-a997-49a9-83ab-815ce60f54dc" />
<img width="1636" height="675" alt="Screenshot 2026-05-29 231249" src="https://github.com/user-attachments/assets/50fd1e57-2c53-4aa0-8aff-8222b000b4e4" />
<img width="1237" height="660" alt="Screenshot 2026-05-29 231519" src="https://github.com/user-attachments/assets/105c8c9a-266d-485e-bb14-76aa1981913a" />
<img width="948" height="935" alt="Screenshot 2026-05-29 231845" src="https://github.com/user-attachments/assets/1db50e37-5643-42d7-84c2-0cac0dcd02bc" />

