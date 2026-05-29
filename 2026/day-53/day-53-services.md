## Day 53 – Kubernetes Services

### What Problem Services Solve
Pods in Kubernetes are temporary. If a Pod crashes or gets recreated, its IP address changes.
This creates a problem because applications cannot reliably communicate using changing Pod IPs.

Kubernetes Services solve this problem by providing:
- A stable IP address
- A stable DNS name
- Load balancing across multiple Pods

Services sit in front of Pods and route traffic to healthy Pods automatically.

--- 

# Deployment Used
## app-deployment.yaml
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

This Deployment creates 3 Nginx Pods with the label:

app: web-app

The Services use this label selector to route traffic to the Pods.
