# 🚀 Kubernetes Guestbook Application on AWS EKS

## 📌 Overview

This project demonstrates the deployment of a multi-tier Guestbook application on Amazon EKS using Kubernetes.

It covers key areas:
- Storage (dynamic & static)
- Networking (Kubernetes services)
- Configuration management (ConfigMaps & Secrets)

The application showcases multiple approaches to configuration:
- Hardcoded environment variables
- ConfigMap-based configuration
- Secret-based configuration

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
- Implemented PVC with automatic PV provisioning  
- Verified persistence after pod restart  

---

### 2. Static Storage (hostPath)
- Created manual PersistentVolume  
- Compared behavior with dynamic provisioning  
- Observed node dependency limitations  

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
- Injected environment variables from Secret  
- Demonstrated `base64` vs `stringData`  

---

## 🧪 Testing Performed

- Verified persistence after pod restart (EBS)  
- Compared data behavior: hostPath vs EBS  
- Tested frontend → Mongo connectivity  
- Validated environment variable injection  
- Debugged PVC Pending, scheduling, and networking issues  


