# 🚀 End-to-End MLOps Project: Scalable ML Pipeline with AWS, Docker & Streamlit  

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)  
![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazon-aws)  
![Docker](https://img.shields.io/badge/Docker-Containerization-blue?logo=docker)  
![CI/CD](https://img.shields.io/badge/GitHub_Actions-CI/CD-black?logo=github-actions)  
![Streamlit](https://img.shields.io/badge/Streamlit-Web_App-ff4b4b?logo=streamlit)  
![Terraform](https://img.shields.io/badge/Terraform-Infrastructure_as_Code-purple?logo=terraform)  

---

## 📌 Project Overview  

This project demonstrates a **production-ready MLOps pipeline** that takes raw data all the way to a **deployed ML model** served through a **Streamlit web app**.  

The system is designed with **modularity, scalability, and automation** in mind, showcasing best practices across:  

- 🔹 **Data Engineering** (MongoDB, Pandas, Feature Engineering)  
- 🔹 **Model Development** (Scikit-learn, modular pipelines, hyperparameter tuning)  
- 🔹 **MLOps Practices** (logging, exception handling, monitoring)  
- 🔹 **CI/CD** (GitHub Actions → AWS ECS/ECR)  
- 🔹 **Infrastructure as Code** (Terraform for AWS provisioning)  
- 🔹 **Deployment** (Docker + AWS ECS + Streamlit app)  

---

## ⚡ Tech Stack  

| Layer                 | Tools & Services                                                                 |
|-----------------------|----------------------------------------------------------------------------------|
| **Data Source**       | MongoDB Atlas (Cloud NoSQL Database)                                             |
| **Processing**        | Python, Pandas, Scikit-learn                                                     |
| **Experimentation**   | Jupyter/Notebooks for EDA & Feature Engineering                                  |
| **Version Control**   | Git, GitHub                                                                      |
| **CI/CD**             | GitHub Actions, Docker, AWS ECR/ECS                                              |
| **Infrastructure**    | Terraform (AWS S3, IAM, ECS, ECR, Secrets)                                       |
| **Model Registry**    | AWS S3                                                                           |
| **Deployment**        | Streamlit Web App, Docker Container                                              |

---

## 🔄 MLOps Workflow  

```mermaid
flowchart TD
    A[📥 Data Source (MongoDB)] --> B[🔍 Data Ingestion]
    B --> C[✅ Data Validation]
    C --> D[⚙️ Data Transformation]
    D --> E[🤖 Model Training]
    E --> F[📊 Model Evaluation]
    F --> G[☁️ Model Registry (AWS S3)]
    G --> H[🚀 Model Deployment (Docker + AWS ECS)]
    H --> I[🌐 Streamlit Web App]
🏗️ Key Features
📥 Data Ingestion: Fetch raw data from MongoDB Atlas into Pandas DataFrames.

🧹 Data Validation & Transformation: Automated schema checks & feature engineering.

🤖 Model Training & Evaluation: Modular ML pipelines with hyperparameter tuning.

☁️ AWS Integration: Store models in S3, deploy via ECR/ECS.

🐳 Containerization: Docker image for portability.

🔄 CI/CD Pipeline: GitHub Actions builds, tests, and deploys on every commit.

🛠️ Infrastructure as Code: Terraform provisions AWS resources (S3, IAM, ECS, ECR).

🌐 Interactive Web UI: Streamlit auto-generates forms based on dataset features.

📈 Scalability: Easily extendable for monitoring, drift detection, and retraining.

⚙️ Setup Instructions
🔹 1. Environment Setup
bash
Copy code
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
🔹 2. MongoDB Setup
Create a MongoDB Atlas cluster.

Create a DB user and whitelist IP (0.0.0.0/0).

Copy the connection string.

Set environment variable:

Linux/Mac (bash):

bash
Copy code
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/myDB"
Windows (PowerShell):

powershell
Copy code
$env:MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/myDB"
🔹 3. AWS Setup
Create IAM user with AdministratorAccess.

Store AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY.

Create an S3 bucket:

ini
Copy code
MODEL_BUCKET_NAME = "<your-bucket-name>"
AWS_DEFAULT_REGION = "<your-region>"
Export credentials:

bash
Copy code
export AWS_ACCESS_KEY_ID="XXXX"
export AWS_SECRET_ACCESS_KEY="XXXX"
export AWS_DEFAULT_REGION="us-east-1"
🔹 4. Run Training Locally
bash
Copy code
python demo.py
🔹 5. Dockerize & Deploy
bash
Copy code
docker build -t vehicleproj .
docker run -p 5080:5080 vehicleproj
🔹 6. CI/CD (GitHub Actions → AWS ECS)
Add GitHub secrets:

AWS_ACCESS_KEY_ID

AWS_SECRET_ACCESS_KEY

AWS_DEFAULT_REGION

ECR_REPO

Every push to main triggers:

Docker build

Push to ECR

ECS task update

Streamlit app live on EC2/ECS

🌐 Streamlit Web App
Auto-generates input forms based on dataset schema.

Allows predictions via trained model.

Deployed on AWS ECS, accessible at:

cpp
Copy code
http://<public-ip>:5080
🔮 Future Enhancements
📊 Model Monitoring & Drift Detection

🔄 Automated Retraining

🧩 Multi-model A/B Testing

📡 Real-time Streaming Data Support

📜 License
This project is licensed under the MIT License.




