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

<img width="1837" height="950" alt="Screenshot 2026-05-29 224958" src="https://github.com/user-attachments/assets/c8acca1e-d14a-43ae-8c54-497d989cbd54" />
<img width="1506" height="645" alt="Screenshot 2026-05-29 225225" src="https://github.com/user-attachments/assets/25d63556-2754-4c00-966a-2771806fb791" />
<img width="1288" height="579" alt="Screenshot 2026-05-29 225252" src="https://github.com/user-attachments/assets/d7c92ae5-b4ac-4802-9f2c-4a64c79b3721" />
<img width="675" height="398" alt="Screenshot 2026-05-29 225311" src="https://github.com/user-attachments/assets/e50298f2-8c89-4151-87ab-3a9369430291" />
<img width="1636" height="675" alt="Screenshot 2026-05-29 231249" src="https://github.com/user-attachments/assets/d6c50f6f-df58-4460-b772-897e617d221d" />
<img width="1237" height="660" alt="Screenshot 2026-05-29 231519" src="https://github.com/user-attachments/assets/270e74dc-ca2c-4099-936a-d993b81bbfbb" />
<img width="1378" height="769" alt="Screenshot 2026-05-30 003202" src="https://github.com/user-attachments/assets/c94f6657-8a14-43cc-b3f2-96a49bac39fb" />
<img width="1436" height="779" alt="Screenshot 2026-05-30 004614" src="https://github.com/user-attachments/assets/021cca70-28c4-43f2-8e54-8682da960643" />
<img width="801" height="945" alt="Screenshot 2026-05-30 004742" src="https://github.com/user-attachments/assets/a012bd4b-f045-4daf-a6e9-ba8a3f340edf" />
<img width="1090" height="719" alt="Screenshot 2026-05-30 005440" src="https://github.com/user-attachments/assets/9d5dc334-4c11-4ae9-8deb-0c6f5fc0adfa" />
<img width="1502" height="402" alt="Screenshot 2026-05-30 005807" src="https://github.com/user-attachments/assets/8e6e6cef-7bc6-4ba6-a548-47a00d1b2eac" />
<img width="976" height="948" alt="Screenshot 2026-05-30 010053" src="https://github.com/user-attachments/assets/bebf354d-1c7e-4278-920a-143f63a1530d" />
<img width="1252" height="944" alt="Screenshot 2026-05-30 010546" src="https://github.com/user-attachments/assets/0a5d37b0-d98c-43f8-8539-309835528e10" />
<img width="1613" height="963" alt="Screenshot 2026-05-30 012244" src="https://github.com/user-attachments/assets/04863b92-353b-4ceb-bfde-f824bf5bb08a" />
<img width="928" height="296" alt="Screenshot 2026-05-30 012338" src="https://github.com/user-attachments/assets/9c35c8a9-64e9-47e9-a1d9-780c26d006d8" />
