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

### 
