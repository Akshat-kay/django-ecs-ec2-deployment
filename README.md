### 📄 `README.md`

```markdown
# 🚀 Django Web App Deployment on AWS ECS (EC2 Launch Type)

This project demonstrates how to containerize a Django application, push it to Amazon ECR, and deploy it using **Amazon ECS with EC2 launch type**.

---

## 🛠️ Tech Stack

- **Django** (Python Web Framework)
- **Docker** (Containerization)
- **Amazon ECR** (Elastic Container Registry)
- **Amazon ECS** (Elastic Container Service using EC2 launch type)
- **Amazon EC2** (for container runtime)
- **GitHub** (Version Control & Code Hosting)

---

## 🌐 Live Demo

Visit the deployed app:  
**http://<your-ec2-public-ip>**

> Replace `<your-ec2-public-ip>` with your actual EC2 IP address. (e.g., `http://3.91.155.190`)

---

## 🧱 Project Structure

```

DevOps-Project-04/
├── hello\_world\_django\_app/
│   ├── **init**.py
│   ├── settings.py
│   ├── urls.py
│   ├── views.py
│   ├── wsgi.py
│   └── templates/
│       └── hello.html
├── Dockerfile
├── manage.py
├── requirements.txt

````

---

## 📦 Docker Setup

### Step 1: Build Docker Image

```bash
docker build -t hello-world-django-app .
````

### Step 2: Tag & Push to ECR

```bash
aws ecr get-login-password | docker login --username AWS --password-stdin <aws-account-id>.dkr.ecr.<region>.amazonaws.com
docker tag hello-world-django-app:latest <your-ecr-repo-uri>
docker push <your-ecr-repo-uri>
```

---

## 🚢 ECS EC2 Deployment

1. Launch an EC2 instance and install Docker and ECS agent.
2. Register the instance with your ECS cluster.
3. Create a Task Definition with the ECR image.
4. Run the task in your ECS cluster using EC2 launch type.
5. Open the security group for ports 80/8000.

---

## 🖼️ UI Preview

The deployed page renders a clean `hello.html` page with a styled background and heading:

```html
<h1>🎉 Deployed Django on ECS!</h1>
```

---

## ✅ What I Learned

* How to containerize a Django project
* How to push Docker images to AWS ECR
* How to deploy apps using ECS with EC2
* How to debug port issues, database configs, and template loaders
* How to use `sqlite3` with Django on EC2

---

## 🧠 Future Improvements

* Automate ECS deployment using CI/CD
* Use RDS instead of SQLite
* Set up domain and SSL with Route 53 & ACM

---

## 📬 Connect with Me

👤 [Akshat-kay on GitHub](https://github.com/Akshat-kay)
📫 [LinkedIn](https://linkedin.com/in/786AKSHATK/)

---


