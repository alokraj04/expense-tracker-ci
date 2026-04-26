# 🚀 Expense Tracker CI/CD Pipeline with AWS Deployment

A production-grade CI/CD pipeline for an Expense Tracker application
that automates build, testing, security scanning, containerization, and
cloud deployment.

This project simulates a real-world DevOps workflow by deploying
containerized services on AWS using ECS, Application Load Balancer, and
PostgreSQL.

------------------------------------------------------------------------

## 📌 Features

-   Automated CI/CD using GitHub Actions\
-   Dockerized backend and frontend services\
-   Secure image storage in AWS Elastic Container Registry (ECR)\
-   Continuous security scanning using Trivy\
-   Automated backend testing using Maven\
-   Artifact sharing across jobs\
-   Scheduled pipeline execution (cron-based)\
-   Commit SHA-based image versioning

------------------------------------------------------------------------

## 🧱 Tech Stack

**Backend:** Java 17, Spring Boot, Maven\
**Frontend:** Node.js 20, Vite\
**CI/CD:** GitHub Actions\
**Containerization:** Docker\
**Cloud:** AWS (ECR, ECS, ALB)\
**Database:** PostgreSQL\
**Security:** Trivy

------------------------------------------------------------------------

## 🔄 CI/CD Workflow

Push / PR / Schedule ↓ Build Backend & Frontend ↓ Testing ↓ Security
Scan (Trivy) ↓ Build Docker Images ↓ Push to AWS ECR ↓ Deploy to AWS ECS
↓ Load Balanced via ALB

------------------------------------------------------------------------

## ☁️ AWS Deployment Architecture

-   Deployed containerized services on AWS ECS (Fargate)
-   Used Application Load Balancer (ALB) for public access
-   Configured Target Groups for routing and health checks
-   Integrated PostgreSQL as the primary database
-   Enabled high availability and automatic service recovery
-   Managed environment variables securely

------------------------------------------------------------------------

## ⚙️ Workflow Triggers

-   Push to `main`
-   Pull requests to `main`
-   Manual trigger (`workflow_dispatch`)
-   Scheduled runs (weekdays)

------------------------------------------------------------------------

## 🧪 Jobs Breakdown

### Build Backend

mvn package -DskipTests

### Build Frontend

npm ci npm run build

### Run Tests

mvn clean test

### Security Scan

-   Filesystem scan using Trivy\
-   Report stored as artifact

### Build & Push to ECR

docker build -t `<ECR_REGISTRY>`{=html}/backend:latest . docker push
`<ECR_REGISTRY>`{=html}/backend:latest

### Image Scan

-   Docker image scanning using Trivy

------------------------------------------------------------------------

## 🔐 Required GitHub Secrets

-   AWS_ACCESS_KEY_ID\
-   AWS_SECRET_ACCESS_KEY

------------------------------------------------------------------------

## 🌍 GitHub Variables

-   AWS_REGION

------------------------------------------------------------------------

## 📦 Artifacts

-   Backend JAR file\
-   Frontend build (`dist/`)\
-   Trivy scan reports

------------------------------------------------------------------------

## 🛡️ Security

-   Filesystem vulnerability scanning\
-   Docker image scanning\
-   Non-blocking security checks

------------------------------------------------------------------------

## ⚡ Key Highlights

-   Parallel frontend & backend builds\
-   Job orchestration using `needs`\
-   Production-like AWS deployment (ECS + ALB + DB)\
-   Image versioning using commit SHA\
-   End-to-end DevOps pipeline

------------------------------------------------------------------------

## 🚧 Future Improvements

-   Integrate SonarQube\
-   Add Slack/email notifications\
-   Implement Blue-Green deployment on ECS\
-   Fail pipeline on critical vulnerabilities\
-   Add Infrastructure as Code (Terraform)

------------------------------------------------------------------------

## 👨‍💻 Author

**Alok Raj**
