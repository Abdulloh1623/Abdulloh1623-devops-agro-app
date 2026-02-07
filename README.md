# 🌾 Agro App — Cloud-Native DevOps Platform

This project demonstrates a **complete Cloud-Native DevOps workflow** using **Kubernetes, Helm, GitHub Actions, ArgoCD, Prometheus, Grafana, and Loki**.

The application is containerized, deployed via Helm, continuously delivered using GitOps (ArgoCD), and fully observable with monitoring and logging.

---

## 🧱 Architecture Overview

The system follows modern cloud-native best practices:

- 🐳 **Containerized Application** (Docker)
- ☸️ **Kubernetes Deployment (Minikube)**
- 📦 **Helm Chart** for Infrastructure as Code
- 🔄 **GitOps with ArgoCD**
- 📊 **Monitoring with Prometheus & Grafana**
- 📝 **Centralized Logging with Loki**
- 🚀 **CI/CD using GitHub Actions**

### High-Level Architecture

```

Developer → GitHub → GitHub Actions → Docker Hub
↓
ArgoCD pulls Helm chart from GitHub
↓
Kubernetes deploys application
↓
Prometheus scrapes metrics
↓
Grafana visualizes dashboards
↓
Loki stores logs

````

---

## 🛠 Tech Stack

| Layer | Technology |
|------|------------|
| Backend | Python (Flask / FastAPI) |
| Container | Docker |
| Orchestration | Kubernetes (Minikube) |
| Package Manager | Helm |
| GitOps | ArgoCD |
| Monitoring | Prometheus + Grafana |
| Logging | Loki + Promtail |
| CI/CD | GitHub Actions |

---

## ✅ Prerequisites

Before running the project, install:

- Docker Desktop  
- Minikube  
- kubectl  
- Helm  
- Git  

---

## 🚀 How to Run the Project

### 1️⃣ Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Abdulloh1623-devops-agro-app.git
cd Abdulloh1623-devops-agro-app
````

### 2️⃣ Start Minikube

```bash
minikube start
```

### 3️⃣ Install ArgoCD

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Expose ArgoCD UI:

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Open in browser:
👉 [https://localhost:8080](https://localhost:8080)

Login:

* **Username:** admin
* **Password:**

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode
```

---

## 📦 Deploy Application via ArgoCD

Apply ArgoCD application:

```bash
kubectl apply -f argocd/projects/agro-app.yaml
```

Then in ArgoCD UI:

1. Click **SYNC**
2. Wait until all components become **Healthy & Synced**

### ✅ Expected ArgoCD View

<img width="1280" height="743" alt="image" src="https://github.com/user-attachments/assets/be452da1-f6d0-4d93-8392-8f7f8e0db362" />


> 👉 Put your ArgoCD screenshot inside `<img width="1280" height="797" alt="image" src="https://github.com/user-attachments/assets/fabb96a8-cd35-4bc1-be15-0d7e467c77fa" />`

---

## 📊 Monitoring with Grafana

Port-forward Grafana:

```bash
kubectl -n monitoring port-forward svc/kube-prometheus-stack-grafana 3000:80
```

Open in browser:
👉 [http://localhost:3000](http://localhost:3000)

Login:

* **Username:** admin
* **Password:** admin (or from Helm values)

### Example Grafana Dashboard

<img width="2559" height="1477" alt="image" src="https://github.com/user-attachments/assets/1a25c07a-9b79-4217-86a6-9b7f5ad78bd6" />


> 👉 Put your Grafana screenshot inside `<img width="2559" height="1477" alt="image" src="https://github.com/user-attachments/assets/7124986d-ec1e-45d9-ae37-8da6113dd84a" />
`

---

## 📝 Logging with Loki

Loki is installed via Helm in the monitoring namespace.

In Grafana:

1. Go to **Explore**
2. Select **Loki**
3. Search logs for your application

---

## 🌐 Application Endpoints

| Endpoint   | Description        |
| ---------- | ------------------ |
| `/`        | Main page          |
| `/health`  | Health check       |
| `/metrics` | Prometheus metrics |

---

## 📁 Repository Structure

```
.
├── app/
│   ├── main.py
│   ├── Dockerfile
│   └── requirements.txt
├── gitops-repo/
│   └── charts/agro-app/
│       ├── templates/
│       └── values.yaml
├── argocd/
│   └── projects/agro-app.yaml
├── .github/
│   └── workflows/pipeline.yml
└── screenshots/
    ├── argocd-dashboard.png
    └── grafana-dashboard.png
```

---

## 🔮 Future Improvements

* Add PostgreSQL database
* Add Horizontal Pod Autoscaler (HPA)
* Configure Alertmanager alerts
* Improve Grafana dashboards
* Add tracing with Tempo

---

## 👨‍💻 Author

**Your Name**
GitHub: [https://github.com/YOUR_USERNAME](https://github.com/YOUR_USERNAME)

```

---

# 📸 **QAYERGA RASM QO‘YISH KERAK?**

GitHub repo ichida shunday papka yarating:

```

/screenshots/

```

Ichiga 2 ta rasm qo‘ying:

1️⃣ **ArgoCD dashboard screenshot**
```

screenshots/argocd-dashboard.png

```

2️⃣ **Grafana dashboard screenshot**
```

screenshots/grafana-dashboard.png

```

Keyin GitHub README’da ular avtomatik ko‘rinadi ✅

---

# 🎯 Agar xohlasangiz:
Men siz uchun:

- README’ni **docx** yoki **pdf** qilib beraman  
- yoki  
- to‘g‘ridan-to‘g‘ri **GitHub repo’ngizga moslab tahrirlab beraman**

Aytishingiz kifoya:  
👉 **“GitHub repoga moslab ber”**
```
