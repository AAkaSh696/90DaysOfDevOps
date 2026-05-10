# Day 51 – Kubernetes Pods

## Four Required Fields

### apiVersion
Defines Kubernetes API version.

### kind
Defines resource type.

### metadata
Stores pod identity like name and labels.

### spec
Defines desired state like image and ports.

---
## nginx, busybox, and third pod manifests and Screenshots
<img width="834" height="482" alt="Screenshot 2026-05-10 223026" src="https://github.com/user-attachments/assets/86524889-e96f-48e3-9216-ce1b428cdc58" />
<img width="449" height="403" alt="Screenshot 2026-05-10 223230" src="https://github.com/user-attachments/assets/60e7c074-a4c6-4235-aedd-775121410394" />
<img width="509" height="371" alt="Screenshot 2026-05-10 223922" src="https://github.com/user-attachments/assets/ebd8e556-eaba-4fb9-87c3-a9da5d8df63e" />
<img width="446" height="242" alt="Screenshot 2026-05-10 225207" src="https://github.com/user-attachments/assets/f7e07f64-78c7-4ef2-9d61-4a035f8fa9b6" />
<img width="934" height="482" alt="Screenshot 2026-05-10 225504" src="https://github.com/user-attachments/assets/4f3de280-9ef6-4d1a-84dc-216c89f34a8e" />
<img width="930" height="475" alt="Screenshot 2026-05-10 230415" src="https://github.com/user-attachments/assets/a23db668-2c9a-4f38-98fd-81f1bf846ec4" />
<img width="931" height="468" alt="Screenshot 2026-05-10 232308" src="https://github.com/user-attachments/assets/ae8901cc-5fdf-4e5f-b969-fb606a7533ae" />


## Difference between imperative (kubectl run) and declarative (kubectl apply -f)
- imperative: command-based and hard to track
- declarative: yaml-based and production preferred

## What happens when you delete a standalone Pod?
When delete a standalone Pod, it is gone forever. There is no controller to recreate it.
