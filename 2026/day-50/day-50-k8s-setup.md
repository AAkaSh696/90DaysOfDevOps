## Day 50 – Kubernetes Architecture and Cluster Setup

## Task 1: Recall the Kubernetes Story
1. Kubernetes was created because docker helps run containers but managing hundreds of containers manually is difficult.
   Kubernetes solves following problems that docker alone can't:
     -  Automate deployment
     -  Scaling
     -  Networking and Load balancing
     -  Auto healing
 2. Kubernetes was originally created by Google and later donated to CNCF(Cloud Native Computing Foundation). It is inspired by Google internal container orchestration system called Borg.
 3. Kubernetes comes from a Greek word meaning "Helmsman/Pilot of a ship"

## Task 2: Draw the Kubernetes Architecture
<img width="1280" height="630" alt="WhatsApp Image 2026-05-07 at 15 38 45" src="https://github.com/user-attachments/assets/45fbcbb7-b084-4c39-aff5-b105a8803fa9" />

1. What happens when ran  "kubectl apply -f pods.yml" :
     - kubectl sends request to API Server
     - API Server validates request
     - Desired state stored in etcd
     - Scheduler selects worker node
     - kubelet receives instructions
     - Container runtime starts container
     - Controller Manager continuously checks desired state
2. What if API Server goes down?
     - Cluster management stops
     - New deployments cannot happen
3. What if Worker Node goes down?
     - Pods on that node become unavailable
     - Controller Manager detects failure
     - Scheduler recreates pods on another healthy node
## Why choose kind:
   - Lightweight
   - User Docker containers
   - Faster setup
   - Perfect for learning

## What is kubeconfig?
- kubeconfig is a configuration file used by kubectl to connect to kubernetes clusters.
- It contains:
    - cluster info
    - user credentials
    - contexts
- Default Location
  ~/.kube/config

## What each kube-system pod does
| Pod                     | Purpose                 |
| ----------------------- | ----------------------- |
| kube-apiserver          | Front door of cluster   |
| etcd                    | Stores cluster data     |
| kube-scheduler          | Assigns pods to nodes   |
| kube-controller-manager | Maintains desired state |
| kube-proxy              | Networking              |
| coredns                 | Internal DNS            |
| kindnet                 | Pod networking          |


