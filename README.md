# clo835-lab3
# 🚀 Kubernetes Guestbook Application on AWS EKS

## 📌 Overview
This project demonstrates deployment of a multi-tier Guestbook application on Amazon EKS using Kubernetes. It covers storage, networking, and configuration management concepts including dynamic provisioning, static volumes, ConfigMaps, and Secrets. The objective of this project is to build and deploy your application on Amazon EKS using persistent storage, K8s service of type LoadBalancer and K8s secrets to access
MongoDB. The application will use hardcode the COLOR as env variable, use K8s ConfigMap, & secrets  to configure background color.
---

## 🏗️ Architecture

User → AWS LoadBalancer → Frontend Service → Frontend Pods → Mongo Service → Mongo Pod → Storage

---

## ⚙️ Technologies Used

- AWS EKS
- Kubernetes
- Docker
- kubectl
- AWS EBS
- YAML

---

## 📂 Project Structure
clo835-lab3/
├── storageclass/
├── hostpath/
├── env_manifests/
├── manifests_config_maps/
├── manifests_secrets/
└── README.md


---

## 🚀 Features Implemented

### 1. Dynamic Storage (EBS)
- Created StorageClass using AWS EBS
- Used `WaitForFirstConsumer` binding mode
- Implemented PVC and automatic PV provisioning
- Verified persistence after pod restart

---

### 2. Static Storage (hostPath)
- Created manual PersistentVolume
- Compared behavior with dynamic provisioning
- Observed node dependency and storage limitations

---

### 3. Kubernetes Services
- ClusterIP → internal communication (MongoDB)
- LoadBalancer → external access via AWS ELB
- NodePort → manual external exposure

---

### 4. ConfigMap
- Externalized application configuration
- Injected environment variables into pod
- Verified dynamic updates

---

### 5. Secret
- Managed sensitive configuration securely
- Used environment variables from Secret
- Demonstrated base64 encoding vs stringData

---

## 🧪 Testing Performed

- Verified pod restart persistence (EBS)
- Compared data behavior in hostPath vs EBS
- Tested service connectivity (frontend → Mongo)
- Validated environment variable injection
- Debugged PVC Pending, pod scheduling, and service issues

---

## 🔍 Key Learnings

- Difference between PV, PVC, and StorageClass
- Dynamic vs Static provisioning
- Kubernetes service types and use cases
- ConfigMap vs Secret usage
- Importance of namespaces and labels
- Real-world debugging of Kubernetes issues

---

## 📸 Screenshots

(Will add VS Code and browser screenshots here)

---

## 🧠 Future Improvements

- Add CI/CD pipeline using GitHub Actions
- Deploy using Helm charts
- Implement Ingress instead of LoadBalancer
- Add monitoring (Prometheus + Grafana)

---

## 👩‍💻 Author

**Varnika Bassi**  
AWS Certified Solutions Architect – Associate  
Aspiring Cloud Engineer

