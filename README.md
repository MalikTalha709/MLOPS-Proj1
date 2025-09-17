# 🚀 End-to-End MLOps Project — Vehicle Data Pipeline  

An end-to-end **MLOps pipeline** that demonstrates how to take a machine learning project from **data ingestion ➝ deployment ➝ monitoring** using modern tools and best practices.  
This project is designed to impress recruiters by showcasing skills in **Data Science + DevOps + Cloud Engineering**.  

---

## 📌 Project Overview  

This project demonstrates the **full lifecycle of ML in production**:  

- Data ingestion from **MongoDB Atlas**  
- EDA, feature engineering, preprocessing  
- Model training, evaluation, and versioning  
- Deployment pipeline with **Docker, GitHub Actions, and AWS ECS**  
- Infrastructure as Code with **Terraform/CloudFormation**  
- Monitoring and logging with custom utilities  
- User-facing app built with **Streamlit**  

> 🏆 The goal: **Showcase industry-level MLOps skills** in a single project.  

---

## 🏗️ System Architecture  

```mermaid
flowchart TD
    A[MongoDB Atlas] -->|Ingestion| B[Data Pipeline]
    B --> C[EDA & Preprocessing]
    C --> D[Model Training]
    D --> E[Model Evaluation]
    E -->|Push| F[S3 Model Registry]
    F --> G[CI/CD via GitHub Actions]
    G --> H[ECR + ECS Deployment]
    H --> I[Streamlit Web App 🚀]
⚡ Tech Stack
Languages & Libraries: Python 3.10, Pandas, Scikit-learn, PyYAML, Boto3

Data Storage: MongoDB Atlas, AWS S3

ML Pipeline: Modular components (Ingestion → Validation → Transformation → Training → Evaluation → Pusher)

CI/CD: GitHub Actions, Self-hosted Runners, Docker, AWS ECR/ECS

Infra as Code: Terraform / CloudFormation

Cloud Services: AWS IAM, S3, ECR, ECS, EC2

Frontend: Streamlit (auto-form UI for predictions)

Logging & Monitoring: Custom Logger + Exception Handler

✨ Key Features
✅ Data ingestion from MongoDB Atlas
✅ EDA + Feature Engineering notebooks
✅ Data validation using YAML schema
✅ Reusable preprocessing pipelines
✅ Model training with evaluation & drift detection
✅ Model registry on AWS S3
✅ End-to-end CI/CD using GitHub Actions + AWS ECS
✅ Containerized with Docker & deployed via ECS
✅ Streamlit UI with auto-generated input forms
✅ Infrastructure automation with Terraform/CloudFormation

🔄 Project Workflow
Environment Setup

setup.py and pyproject.toml for local packages

Virtual environment (conda create -n vehicle python=3.10)

Data Source (MongoDB Atlas)

Create cluster → Add IP access → Create DB user → Load dataset

Data Pipeline

Ingestion → Validation → Transformation → Training → Evaluation → Pusher

AWS Integration

IAM Roles, S3 bucket (my-model-mlopsproj), Model Registry

Access keys configured as environment variables

CI/CD with GitHub Actions

Build Docker image → Push to ECR → Deploy on ECS

Secrets stored in GitHub → Automated pipeline on push

Streamlit Web App

/train → retrain model on demand

/predict → input features via auto-generated form

Hosted on ECS, accessible via public IP:5080

☁️ Infrastructure (AWS)
S3 → Model & artifact storage

IAM → Secure user and role policies

ECR → Store Docker images

ECS + EC2 → Deployment of ML service

Terraform/CloudFormation → Automated provisioning

⚙️ CI/CD Pipeline
On every commit →

Build Docker image

Push to AWS ECR

Update ECS task definition

Deploy latest version of app automatically 🚀

🎨 Streamlit App
Auto-generates forms based on dataset features

Displays model predictions

/training route available for retraining

Deployed on AWS ECS → accessed via http://<EC2-IP>:5080

🛠️ How to Run Locally
bash
Copy code
# Clone the repository
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>

# Create environment
conda create -n vehicle python=3.10 -y
conda activate vehicle

# Install dependencies
pip install -r requirements.txt

# Set MongoDB & AWS credentials
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster..."
export AWS_ACCESS_KEY_ID="xxxx"
export AWS_SECRET_ACCESS_KEY="xxxx"
export AWS_DEFAULT_REGION="us-east-1"

# Run training pipeline
python demo.py

# Run Streamlit app
streamlit run app.py
🚀 Future Improvements
Add model monitoring (Prometheus + Grafana)

Implement unit/integration tests with pytest

Deploy with Kubernetes (EKS)

Automate retraining with Airflow

👨‍💻 Author
Malik Talha
MLOps Engineer | Data Scientist
📧 Email: [maliktalha1515@gmail.com]

⭐ If you like this project, don’t forget to star the repo!
