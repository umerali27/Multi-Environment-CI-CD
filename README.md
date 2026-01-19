# Multi-Environment CI/CD Deployment (Dev / Staging / Prod)

## Overview

This project demonstrates a **production-grade multi-environment CI/CD pipeline** for a containerized multi-tier web application.  
The same application is deployed across **DEV, STAGING, and PROD environments** using Kubernetes namespaces, Helm, and Jenkins.

The goal of this project is to showcase **environment isolation, promotion-based deployments, and enterprise CI/CD workflows** commonly used in real-world DevOps teams.

---

## Architecture
![Infrastructure Image](https://github.com/umerali27/Multi-Environment-CI-CD/blob/main/Dev%2Cstag%2Cprod.png)

---

## Environment Strategy

| Environment | Purpose |
|------------|--------|
| DEV | Active development and testing |
| STAGING | Pre-production validation |
| PROD | Production deployment |

Each environment:
- Runs in a **separate Kubernetes namespace**
- Uses the **same Helm chart**
- Has **environment-specific values**

---


---

## CI/CD Workflow

1. Developer pushes code to GitHub
2. Jenkins pipeline is triggered
3. Docker images are built and pushed
4. Application is deployed to DEV
5. Application is promoted to STAGING
6. Manual approval is required
7. Application is deployed to PROD

---

## Tools & Technologies

- Docker
- Jenkins
- Kubernetes
- Helm
- GitHub

---

## Project Status

✔ Multi-environment setup completed  
✔ Promotion-based deployment implemented  
✔ Production-ready CI/CD workflow

Author 
Umer Ali

