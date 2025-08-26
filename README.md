# 🚀 Nginx Kubernetes Deployment on Amazon Linux EC2 + Minikube

This project sets up:
- A **custom Nginx Docker image** with own `index.html`
- A **Kubernetes Deployment** and **NodePort Service**
- Running on **Amazon Linux 2 EC2** instance with **Minikube**

---

## 🛠️ Step 1: Install Dependencies (EC2)
```bash
# Update system
sudo yum update -y

# Install Docker
sudo yum install -y docker
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker ec2-user

# Install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

# Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

