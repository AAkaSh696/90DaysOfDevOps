# Day 44 – Secrets, Artifacts & Running Real Tests in CI

## Secrets
- Stored sensitive data securely
- Used ${{ secrets.SECRET_NAME }}
- GitHub masks secret values in logs

### Why not print secrets?
Because its the sensitiv data and logs may expose sensitive data that can lead to  security risks

### Real-world usage of Artifacts
- It store build outputs that can be needed for information purposes/
- It also needs to share files between jobs

## Caching
- Cached dependencies of python 
- Speeds up pipeline
- Stored in GitHub cache system
