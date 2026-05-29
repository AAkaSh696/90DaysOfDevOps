# Day 54 – Kubernetes ConfigMaps & Secrets

## What are ConfigMaps?

ConfigMaps are used to store non-sensitive configuration data in Kubernetes such as environment variables, ports, configuration files, and application settings.

Examples:

* App environment
* Debug mode
* Nginx configuration

---

## What are Secrets?

Secrets are used to store sensitive information securely in Kubernetes.

Examples:

* Passwords
* API keys
* Database credentials

---

## Environment Variables vs Volume Mounts

### Environment Variables

Used for:

* Simple key-value settings

Limitation:

* Values do not update automatically after pod startup

---

### Volume Mounts

Used for:

* Full configuration files

Advantage:

* Updates automatically propagate inside running containers

---

## Base64 Encoding vs Encryption

Kubernetes Secrets use base64 encoding.

Base64 is:

* Encoding ❌
* Not encryption ❌

Anyone with cluster access can decode it.

The real security benefits come from:

* RBAC
* Restricted access
* Encryption at rest
* Secure secret handling

---

## ConfigMap Update Behavior

When a ConfigMap is mounted as a volume:

* Kubernetes updates the mounted files automatically

When used as environment variables:

* Values are fixed at pod startup
* Pod restart required for updates

---
<img width="1378" height="769" alt="Screenshot 2026-05-30 003202" src="https://github.com/user-attachments/assets/266af246-dc13-4f8c-8373-7113d78364af" />
<img width="1436" height="779" alt="Screenshot 2026-05-30 004614" src="https://github.com/user-attachments/assets/df8016ff-e71f-42be-bbcb-42706cc8d090" />
<img width="801" height="945" alt="Screenshot 2026-05-30 004742" src="https://github.com/user-attachments/assets/a80d38d6-05fa-4440-82fb-116405ecef8b" />
<img width="1090" height="719" alt="Screenshot 2026-05-30 005440" src="https://github.com/user-attachments/assets/ccfeea58-ccdd-48fd-9ec4-925a2459eb4b" />
<img width="1502" height="402" alt="Screenshot 2026-05-30 005807" src="https://github.com/user-attachments/assets/d4411ca3-20f0-4d25-b540-c800b2d65e2e" />
<img width="976" height="948" alt="Screenshot 2026-05-30 010053" src="https://github.com/user-attachments/assets/06f0fc17-5eb2-4a45-a7cc-c65d77915377" />
<img width="1252" height="944" alt="Screenshot 2026-05-30 010546" src="https://github.com/user-attachments/assets/f85e67b2-4d9a-4aa3-a53f-3d4488c5e57f" />
<img width="1613" height="963" alt="Screenshot 2026-05-30 012244" src="https://github.com/user-attachments/assets/b1a1d77f-474c-4ab3-aad5-d6fec71d33da" />
<img width="928" height="296" alt="Screenshot 2026-05-30 012338" src="https://github.com/user-attachments/assets/e102d6d9-7764-44f8-87ef-1f30e211cd31" />
