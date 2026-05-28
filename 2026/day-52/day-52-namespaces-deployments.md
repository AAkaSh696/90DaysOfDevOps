# Day 52 – Kubernetes Namespaces and Deployments

## What are Namespaces?

Namespaces are used to organize and isolate Kubernetes resources.

They help:
- separate environments
- avoid naming conflicts
- manage teams and applications

Example:
- dev
- staging
- production

---

## What is a Deployment?

Deployment is a Kubernetes controller that manages Pods.

It provides:
- self-healing
- scaling
- rolling updates
- rollback support

---

## Deployment Manifest Explanation

### replicas
Defines desired number of Pods.

### selector
Matches Pods managed by Deployment.

### template
Blueprint for Pod creation.

---

## Standalone Pod vs Deployment

### Standalone Pod
If deleted:
- permanently gone

### Deployment Pod
If deleted:
- automatically recreated

---

## Scaling

### Imperative
kubectl scale deployment

### Declarative
Update replicas in YAML

---

## Rolling Update

Kubernetes updates Pods gradually without downtime.

---

## Rollback

kubectl rollout undo restores previous working version.

## Screenshots 
<img width="1172" height="852" alt="Screenshot 2026-05-28 123233" src="https://github.com/user-attachments/assets/0e1e44f3-85f5-4ee7-a91a-2b7564513a20" />
<img width="1297" height="870" alt="Screenshot 2026-05-28 123623" src="https://github.com/user-attachments/assets/e98b9e83-72e3-470b-8513-e406b679598f" />
<img width="1097" height="450" alt="Screenshot 2026-05-28 123730" src="https://github.com/user-attachments/assets/47fc82ed-f7d0-47e0-b9a5-bf9aa3b1dcf7" />
<img width="1075" height="955" alt="Screenshot 2026-05-28 124005" src="https://github.com/user-attachments/assets/2dbffd9e-8a51-4241-ab05-d814b5577224" />
<img width="1207" height="792" alt="Screenshot 2026-05-28 124437" src="https://github.com/user-attachments/assets/9d8f7e78-afc2-4db6-814d-68c0f56bfa4c" />
<img width="1048" height="499" alt="Screenshot 2026-05-28 124803" src="https://github.com/user-attachments/assets/c310dbc1-79ef-485b-8a47-26584face546" />
<img width="1102" height="740" alt="Screenshot 2026-05-28 124916" src="https://github.com/user-attachments/assets/ae15f584-4427-4622-823e-f5137996fb07" />
