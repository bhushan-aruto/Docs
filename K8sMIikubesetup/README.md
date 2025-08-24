

---

# 📝 Kubernetes (K8s) Setup with Minikube on Ubuntu

### 1️⃣ Remove Old Installations

```bash
sudo rm -rf ~/.minikube
sudo rm -rf /usr/local/bin/minikube /usr/bin/minikube
sudo rm -rf /usr/local/bin/kubectl /usr/bin/kubectl
sudo apt remove --purge -y docker* containerd* podman* || true
sudo apt autoremove -y
```

---

### 2️⃣ Update System & Install Dependencies

```bash
sudo apt update -y
sudo apt upgrade -y
sudo apt install -y curl apt-transport-https conntrack
```

---

### 3️⃣ Install Docker (Required for Minikube Docker Driver)

```bash
sudo apt install -y docker.io
sudo usermod -aG docker $USER
newgrp docker   # Apply Docker group without logging out
docker --version
```

---

### 4️⃣ Install kubectl

```bash
curl -LO "https://dl.k8s.io/release/$(curl -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
kubectl version --client
```

---

### 5️⃣ Install Minikube

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version
```

---

### 6️⃣ Start Minikube with Docker Driver (No VM Needed)

```bash
minikube start --driver=docker
```

✅ Verify cluster is running:

```bash
kubectl get nodes
minikube status
```

---

### 7️⃣ Optional: Check Docker Resources Allocated to Minikube

```bash
minikube config view
minikube profile list
```

---

### 8️⃣ Optional: Stop or Delete Minikube Cluster

```bash
minikube stop
minikube delete --all
```

---


