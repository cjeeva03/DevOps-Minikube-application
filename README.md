
# Kubernetes Deployment with Minikube 

Deploy a Dockerized app to a local Kubernetes cluster using Minikube


## Pre-Requisites

 - [Docker Engine](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
    - [Windows](https://docs.docker.com/desktop/setup/install/windows-install/)
    - [Linux](https://docs.docker.com/desktop/setup/install/linux/)
    - [Mac](https://docs.docker.com/desktop/setup/install/mac-install/)
  - [Minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Fwindows%2Fx86-64%2Fstable%2F.exe+download)
  - [Git Bash](https://git-scm.com/install/)
  


## Task

- [Dockerize a simple app](https://github.com/cjeeva03/DevOps-Jenkins-Docker)
- Create Kubernetes manifests (Deployment, Service) 
- Deploy to Minikube 
- Use kubectl to verify pods/services 
- **Bonus:** Add Ingress for local domain-based access 



## Layout

```sh
DevOps-Minikube-application
├── deployment/
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
└── README.md

```
## Quick start (local)

### 1. Dockerize Your App (If Not Already Done)
check README.md
```bash
git clone https://github.com/cjeeva03/DevOps-Jenkins-Docker.git
```

### 2. Load Docker Image into Minikube
Minikube uses its own Docker daemon. Load your image into Minikube and enable ingress:
```bash
minikube image load your-image-name:tag
minikube addons enable ingress
```
### 3. Create Kubernetes Manifests
__yaml files__

- deployment.yaml
- service.yaml
- ingress.yaml

### 4. Deploy to Minikube
Apply the manifests:
```bash
cd deployment
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f ingress.yaml
```
### 5. Verify Deployment
```bash
kubectl get pods
kubectl get services
```
### 6. Access ingress
Windows
- Folder - C:\Windows\System32\drivers\etc
- Open file in admin ```hosts```
- Get your Minikube IP 
```bash 
minikube ip
```
- Add a line like this to the ```hosts``` file
```bash
<minikube ip> myapp.local
```
- Now you can access your app via ```http://myapp.local```

## Roadmap

### commit history
    1. initial commit.
    2. Error faced - [python -m venv venv] Jenkinsfile - Added seperate python docker.
    3. Removed python docker and modified jenkins image
    4. python error fix venv setup.
    5. Re-configured - changed jenkins image to ubuntu image for docker dependency.

