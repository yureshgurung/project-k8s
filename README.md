simple k8s project  


# simple k8s project  
#  Simple Notes App  

This is a simple notes app built with React and Django

---


##  Architecture

<img width="975" height="284" alt="image" src="https://github.com/user-attachments/assets/8d4253c8-4c07-45ee-ba8a-82c3ca2fe1e8" />








## Installation & Setup

### 1. Clone the Repository

```bash
⚠️ Note:This is a simple Kubernetes project where the application code is cloned from this GitHub link for learning and deployment purposes.

git clone https://github.com/LondheShubham153/django-notes-app.git
cd django-notes-app
```

---

### 2. Build Docker Image

```bash
docker build -t notes-app .
```

---

### 3. Run Locally (Docker)

```bash
docker run -d -p 8000:8000 notes-app

```
<img width="975" height="332" alt="image" src="https://github.com/user-attachments/assets/3f260296-1ac1-4b3e-bb0d-62d6aa7f30b6" />


Open in browser:

```
http://localhost:8000
```
<img width="975" height="397" alt="image" src="https://github.com/user-attachments/assets/60f78893-a8a2-4ba2-8af5-32051324dc97" />

---

### 4. Push Image to Docker Hub

```bash
docker tag notes-app <your-dockerhub-username>/notes-k8s:latest
docker push <your-dockerhub-username>/notes-k8s:latest
```
docker image tag notes-k8s:latest yrueshgrg/notes-k8s:latest

docker push yrueshgrg/notes-k8s:latest
<img width="975" height="304" alt="image" src="https://github.com/user-attachments/assets/4644aa68-bcb4-445b-a98c-89d860a37725" />

---

## Kubernetes Deployment

### Apply all resources:

```bash
kubectl apply -f namespace.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

---


##  Access the Application

Since the service type is **ClusterIP**, use port forwarding:

```bash
kubectl port-forward service/notes-app-service -n notes-app 8000:8000 --address=0.0.0.0
```
<img width="975" height="108" alt="image" src="https://github.com/user-attachments/assets/d6ec71cc-1d4a-4fa4-89d0-534d500e7248" />

Now open:

```
http://localhost:8000
```

---
<img width="975" height="473" alt="image" src="https://github.com/user-attachments/assets/27abd72c-528e-4549-9ddc-5e06d2812872" />

##  Verify Deployment

```bash
kubectl get all -n notes-app
```

---

## Tech Stack

* Frontend: React
* Backend: Django
* Containerization: Docker
* Orchestration: Kubernetes

---



---                                   THANK YOU!
