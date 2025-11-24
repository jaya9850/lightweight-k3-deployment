
# 🚀 K3s Kubernetes Cluster Setup on AWS EC2

This repository contains my complete setup of a **lightweight Kubernetes cluster using K3s** on AWS EC2 instances, including deployment files, service files, and node scheduling configuration.

---

## 🧩 **1. K3s Installation Commands**

### 🖥️ Master Node
```bash
curl -sfL https://get.k3s.io | sh - 
sudo systemctl status k3s
sudo cat /var/lib/rancher/k3s/server/node-token
hostname -I
````

### 🖥️ Worker Node

```bash
curl -sfL https://get.k3s.io | K3S_URL="https://<MASTER-IP>:6443" \
K3S_TOKEN="<NODE_TOKEN>" sh -
```

---

## 🌐 **2. Verify Nodes**

```bash
kubectl get nodes
kubectl get nodes -o wide
```

---

## 📦 **3. Deploy Nginx**

Apply deployment file:

```bash
kubectl apply -f nginx-deploy.yaml
```

Check pods:

```bash
kubectl get pods
```

---

## 🌍 **4. Expose Service**

```bash
kubectl apply -f nginx-service.yaml
kubectl get svc
```

---


## ✨ **Output**

## 🖼️ Cluster Status Screenshot

![Cluster Status](Screenshot%202025-11-24%20200429.png)

## 🖼️ Node Overview Screenshot

![Nodes](Screenshot%202025-11-24%20200542.png)

## 🖼️ Deployment Applied Screenshot

![Deployment](Screenshot%202025-11-24%20200220.png)

## 🖼️ Service Screenshot

![Service](Screenshot%202025-11-24%20203346.png)


---






