# Day 49 – DevSecOps

## What is DevSecOps?
DevSecOps means adding security checks directly into the CI/CD pipeline so vulnerabilities are detected early before deployment.

## What you learned about secret scanning and dependency review

- Security should be part of pipeline, not after deployment
- Trivy helps detect vulnerabilities in Docker images
- Dependency review prevents insecure packages
- Secrets should never be exposed in code

## Pipeline Flow

PR → Test → Dependency Check  
Main → Test → Docker → Security Scan → Deploy  

Screenshots:
<img width="1863" height="809" alt="Screenshot 2026-05-06 163402" src="https://github.com/user-attachments/assets/dbbce44b-f327-41a6-b3d8-b0597ea3cc22" />
<img width="1915" height="815" alt="Screenshot 2026-05-06 163446" src="https://github.com/user-attachments/assets/6026cc02-bb4a-4663-8c23-37e1da5b1bef" />
<img width="1890" height="813" alt="Screenshot 2026-05-06 163931" src="https://github.com/user-attachments/assets/d8208754-9aba-4abd-b2e3-780f8619da8b" />
<img width="1912" height="733" alt="Screenshot 2026-05-06 164027" src="https://github.com/user-attachments/assets/78f6da10-6447-4703-9cd6-d736f18fed87" />
<img width="1864" height="915" alt="Screenshot 2026-05-06 170537" src="https://github.com/user-attachments/assets/e90cff42-8b6f-448a-8253-4346cde23eaa" />
<img width="1834" height="806" alt="Screenshot 2026-05-06 170736" src="https://github.com/user-attachments/assets/96843d78-88ca-484b-bc42-d38230e1c7ea" />
<img width="1295" height="751" alt="Screenshot 2026-05-06 171837" src="https://github.com/user-attachments/assets/e43f8dbb-3e50-4c20-92e0-b78246765ab8" />
<img width="1691" height="687" alt="Screenshot 2026-05-06 171851" src="https://github.com/user-attachments/assets/33fb8147-7157-41e6-8769-55662ecf4af7" />
<img width="1267" height="699" alt="Screenshot 2026-05-06 173135" src="https://github.com/user-attachments/assets/e1e400ca-d25b-4583-a1f1-650e17c883dd" />
<img width="1882" height="772" alt="Screenshot 2026-05-06 180206" src="https://github.com/user-attachments/assets/1da420e7-e103-4d45-88c5-7969b07566b6" />

