# Multi-Tier Web Application with CI/CD and Kubernetes

## Project Overview
This project demonstrates a **complete multi-tier web application** with modern **DevOps practices**. 
It includes a **React frontend**, **Flask backend**, and **PostgreSQL database**, 
all **containerized with Docker**, tested locally with `docker-compose`, and 
ready for deployment to **Kubernetes** using **Helm charts**.  

The project also includes a **CI/CD pipeline** using **Jenkins** to automate building, testing, and deploying the application.

---

🏗️ Application Architecture

Architecture Type: Three-Tier Architecture

User
  |
  v
Ingress Controller
  |
  v
Frontend (React)
  |
  v
Backend (Flask REST API)
  |
  v
PostgreSQL Database

Architecture Components

Frontend

React-based UI

Communicates with backend using REST APIs

Backend

Flask REST API

Handles business logic and database communication

Database

PostgreSQL deployed as a container

No application code required (official image used)

CI/CD

Jenkins automates build, test, image creation, and deployment

Orchestration

Kubernetes manages containers

Helm charts handle templated deployments

Ingress exposes the frontend externally
