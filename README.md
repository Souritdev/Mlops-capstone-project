# 🚀 MLOps Capstone Project – End-to-End Cloud ML System  
AWS | Docker | Kubernetes (EKS) | ECR | EC2 Runner | CI/CD | Monitoring | MLflow | DVC  

This capstone project demonstrates a **complete production-grade MLOps pipeline** deployed on AWS using Kubernetes, Docker, CI/CD, and real-time monitoring systems.  
It covers the entire lifecycle: **data → model → deployment → monitoring → automation**.

---

# 🧱 Project Architecture

### **1. Data Pipeline**
- Data ingestion  
- Data validation  
- Data transformation  
- Feature engineering  
- Model training  
- Model evaluation  
- Model registry  
- Model pushing to cloud  

### **2. MLOps Systems**
- MLflow – experiment tracking  
- DVC – data & model versioning  
- Docker – containerization  
- AWS ECR – container registry  
- AWS EKS – production-grade deployment  
- AWS S3 – artifact storage  
- EC2 Self-Hosted Runner – CI/CD automation  
- GitHub Actions – full CI/CD pipeline  
- Prometheus – metrics scraping  
- Grafana – monitoring dashboard  

---

# 🗂️ Folder Structure

```
mlops-capstone-project/
│
├── src/
│   ├── components/
│   ├── data/
│   ├── pipelines/
│   ├── utils/
│   ├── cloud_storage/
│   ├── entity/
│   ├── app.py
│   └── demo.py
│
├── notebook/
├── static/
├── template/
│
├── Dockerfile
├── requirements.txt
├── params.yaml
├── dvc.yaml
├── .dockerignore
├── .gitignore
└── README.md
```

---

# 🌐 AWS Infrastructure Setup

### **1️⃣ AWS IAM User**
- Create user with **AdministratorAccess**  
- Generate access + secret keys  
- Store them securely  

### **2️⃣ AWS S3 Bucket**
- Stores models, artifacts, logs  
- Versioning enabled  

### **3️⃣ AWS ECR**
- Used as Docker image registry  
- GitHub Actions pushes the images directly  

### **4️⃣ AWS EC2 (Self-Hosted Runner)**
- Ubuntu instance  
- Docker installed  
- GitHub runner registered  
- Automates deployment on EKS  

### **5️⃣ AWS EKS Cluster**
- Created using eksctl  
- Node group using EC2  
- Deployed backend ML application via Kubernetes manifests  

---

# 🐳 Docker Setup

Build Docker image:

```
docker build -t capstone-app:latest .
```

Run locally:

```
docker run -p 8888:5000 capstone-app:latest
```

Push to ECR:

Handled via CI/CD pipeline.

---

# 🔄 GitHub CI/CD Workflow

Triggered on every commit to `main` branch:

### **Pipeline Steps**
1. Checkout code  
2. Configure AWS credentials  
3. Build Docker image  
4. Login to Amazon ECR  
5. Push image to ECR  
6. Connect to EC2 / EKS  
7. Apply updated Kubernetes manifests  
8. Restart deployment  

Deployment happens automatically.

---

# ☸️ Kubernetes Deployment (EKS)

### Files Included:
- `deployment.yaml`
- `service.yaml`

### Services:
- LoadBalancer for public access  
- Application listens on **port 5000**

To check resources:

```
kubectl get pods
kubectl get svc
kubectl get deployments
```

Access application:
```
http://<LOAD_BALANCER_EXTERNAL_IP>:5000
```

---

# 📊 Monitoring Setup

### Prometheus
- Scrapes metrics from application  
- Configured on separate EC2 instance  

### Grafana
- Installed on EC2  
- Connects to Prometheus  
- Dashboards created for:
  - Model latency  
  - API health  
  - Pod performance  
  - Node usage  

---

# 🧪 Training Route

Trigger model training:

```
/train
```

This retrains model → evaluates → pushes new version → updates EKS through CI/CD.

---

# 🏁 Final System Outcome

✔ Fully automated ML system  
✔ Cloud-native production deployment  
✔ Real-time monitoring  
✔ CI/CD DevOps integration  
✔ Auto model updates  
✔ End-to-end reproducible pipeline  

---

# 👨‍💻 Author
**Sourit Nandy**  
GitHub: https://github.com/Souritdev/Mlops-capstone-project  
LinkedIn: https://linkedin.com/in/sourit-nandy-7aa8b6209
