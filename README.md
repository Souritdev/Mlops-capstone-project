# 🚀 Capstone MLOps Project – AWS | EKS | Docker | MLflow | DVC | CI/CD

A fully production-grade **Cloud + MLOps pipeline** built as a Capstone Project using  
**AWS EKS, Docker, MLflow, DVC, GitHub Actions, Prometheus, Grafana, and Flask**.

This project demonstrates an **end‑to‑end Machine Learning system** deployed using
modern MLOps and Cloud‑Native architecture.

---

## 🏗️ **Project Architecture**

### ✔ Data Pipeline  
- Data Ingestion  
- Data Validation  
- Feature Engineering  
- Model Training  
- Model Evaluation  
- Model Registry (MLflow)

### ✔ Versioning  
- **DVC** for dataset + pipeline version control  
- **S3** as remote artifact store  

### ✔ Experiment Tracking  
- MLflow UI  
- Model parameters, metrics, artifacts  

### ✔ CI/CD  
- GitHub Actions:  
  - Lint + Test  
  - Build Docker image  
  - Push to AWS ECR  
  - Deploy to AWS EKS  

### ✔ Deployment (Production)  
- Dockerized ML inference API (Flask)  
- Kubernetes Deployment + Service  
- AWS LoadBalancer for public access  
- IAM‑based secure access  

### ✔ Monitoring  
- Prometheus (scraping app metrics)  
- Grafana Dashboards (latency, traffic, CPU, error rate)

---

## ⚙️ **Tech Stack**

### **Languages & Frameworks**
- Python, Flask  
- Bash scripting  

### **MLOps Tools**
- MLflow  
- DVC  
- GitHub Actions  
- Docker  

### **AWS Services**
- EKS (Kubernetes)  
- ECR  
- EC2  
- S3  
- CloudWatch  

### **Observability**
- Prometheus  
- Grafana  

---

## 📁 **Folder Structure**

```
.
├── src/
│   ├── ingestion/
│   ├── preprocessing/
│   ├── training/
│   ├── evaluation/
│   ├── utils/
│   └── app.py
│
├── dvc.yaml
├── params.yaml
├── Dockerfile
├── requirements.txt
├── deployment.yaml
├── service.yaml
└── README.md
```

---

## 🚀 **How to Run Locally**

### 1️⃣ Clone the repository
```
git clone <your-repo-link>
cd <project-folder>
```

### 2️⃣ Install dependencies
```
pip install -r requirements.txt
```

### 3️⃣ Run DVC pipeline
```
dvc repro
```

### 4️⃣ Start MLflow
```
mlflow ui
```

### 5️⃣ Run the API
```
python src/app.py
```

The API will run at:
```
http://127.0.0.1:5000
```

---

## 🐳 **Docker Setup**

### Build Docker image
```
docker build -t capstone-mlops:latest .
```

### Run the container
```
docker run -p 5000:5000 capstone-mlops:latest
```

---

## ☁️ **AWS Deployment Instructions**

### 1️⃣ Push image to ECR  
- Login  
- Tag image  
- Push image  

### 2️⃣ EKS Deployment  
```
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl get svc
```

Copy the **external LoadBalancer URL** → This is your API endpoint.

---

## 📊 **Monitoring Setup**

### Prometheus  
- Add your LoadBalancer endpoint to `prometheus.yml` under `targets`.

### Grafana  
- Add Prometheus as a datasource  
- Import dashboards  
- Visualize metrics

---

## 🏁 **Cleanup**

```
eksctl delete cluster --name <cluster-name>
aws ecr delete-repository --force --repository-name <repo-name>
dvc remote remove myremote
```

---

## 🎯 **Project Outcome**

This Capstone project demonstrates:
- Production-ready ML system  
- Cloud-native deployment  
- Automated CI/CD  
- Container orchestration  
- Advanced observability  
- Complete reproducibility  

Perfect for **MLOps Engineer**, **Cloud Engineer**, or **Backend ML Engineer** roles.

---

## 🧑‍💻 Author
**Sourit Nandy**  
GitHub: https://github.com/Souritdev  
LinkedIn: https://linkedin.com/in/sourit-nandy-7aa8b6209
