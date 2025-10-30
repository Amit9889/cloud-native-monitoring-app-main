# 🚀 Flask Cloud-Native Deployment Project

This project demonstrates how to **develop, containerize, and deploy a Flask web application** using **Docker, AWS ECR, and Amazon EKS (Kubernetes)**.

---

## ✨ Part 1: Run Flask App Locally

1. **Clone the repository**
   ```bash
   git clone <repository_url>
Install dependencies

bash
Copy code
pip3 install -r requirements.txt
Run the app

bash
Copy code
python3 app.py
Access at: http://localhost:5000

🐳 Part 2: Dockerize the Flask Application
Create Dockerfile (use provided file in project root)

Build Docker image

bash
Copy code
docker build -t <image_name> .
Run container

bash
Copy code
docker run -p 5000:5000 <image_name>
Access at: http://localhost:5000

☁️ Part 3: Push Docker Image to AWS ECR
Create ECR repository

python
Copy code
import boto3
ecr = boto3.client('ecr')
ecr.create_repository(repositoryName='my-ecr-repo')
Push image to ECR

bash
Copy code
docker push <ecr_repo_uri>:<tag>
⚙️ Part 4: Deploy on Amazon EKS via Python
Create EKS Cluster and Node Group
(Use AWS Console or eksctl)

Deploy Flask App using Kubernetes API

bash
Copy code
python3 eks.py
Verify resources

bash
Copy code
kubectl get deployments -n default
kubectl get services -n default
kubectl get pods -n default
Expose Service

bash
Copy code
kubectl port-forward service/<service_name> 5000:5000
Access at: http://localhost:5000

🧩 Tech Stack
Backend: Flask, Plotly, psutil

Containerization: Docker

Cloud Services: AWS ECR, EKS

Automation: Python (boto3, kubernetes SDK)

