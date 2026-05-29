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

<img width="1837" height="950" alt="Screenshot 2026-05-29 224958" src="https://github.com/user-attachments/assets/6c9e1cce-d7bb-41f9-a738-2b6de54a808a" />


---

