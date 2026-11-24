# 🐳 Docker Learning – My First Containerized Application

This repository documents my hands-on learning journey with Docker, starting from basic Docker commands to building custom images and running a Python Flask web application inside a Docker container.

## 🎯 Learning Objectives

- Understand Docker images and containers.
- Learn essential Docker CLI commands.
- Download and manage Docker images.
- Run Ubuntu and Nginx containers.
- Create custom Docker images using Dockerfiles.
- Containerize a Python Flask application.
- Understand Docker port mapping and container lifecycle management.

## 🛠️ Technologies Used

- Docker Desktop
- Docker CLI
- Docker Engine
- Python 3.12
- Flask
- Ubuntu
- Nginx

## 📂 Project Structure

```text
docker-learning/
│
├── Dockerfile
├── app.py
├── requirements.txt
└── README.md
```

## 🐳 Docker Practicals

### 1. Running the Hello World Container

```bash
docker run hello-world
```

Verified Docker installation by running the first container.

### 2. Working with Docker Images

```bash
docker pull nginx
docker pull ubuntu
docker images
```

Downloaded and explored Ubuntu and Nginx images from Docker Hub.

### 3. Running an Nginx Container

```bash
docker run -d -p 8000:80 --name krushnali-nginx nginx
```

Started an Nginx web server inside a Docker container and accessed it through:

`http://localhost:8000`

### 4. Running an Ubuntu Container

```bash
docker run -it ubuntu bash
```

Explored the Ubuntu environment using Linux commands:

```bash
cat /etc/os-release
ls
pwd
exit
```

### 5. Building a Custom Python Docker Image

Created a Python application and packaged it into a custom Docker image.

```bash
docker build -t my-python-app .
```

Executed the container:

```bash
docker run my-python-app
```

### 6. Dockerizing a Flask Web Application

Created a simple Flask application and built a custom Docker image.

Build the image:

```bash
docker build -t y-python-web .
```

Run the container:

```bash
docker run -d -p 8000:5000 --name my-flask-app y-python-web
```

Access the application:

`http://localhost:8000`

## 📄 Dockerfile

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

EXPOSE 5000

CMD ["python", "app.py"]
```

## 📚 Key Docker Commands Learned

| Command | Purpose |
|---|---|
| `docker --version` | Check Docker version |
| `docker info` | View Docker Engine information |
| `docker pull` | Download an image |
| `docker images` | List available images |
| `docker build` | Build a custom image |
| `docker run` | Create and run a container |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers |
| `docker stop` | Stop a container |
| `docker start` | Start a stopped container |
| `docker logs` | View container logs |
| `docker inspect` | Inspect container details |

## 💡 Key Concepts Learned

- Difference between Docker images and containers.
- Dockerfile instructions: `FROM`, `WORKDIR`, `COPY`, `RUN`, `EXPOSE`, and `CMD`.
- Docker build context.
- Container port mapping.
- Running Linux environments inside containers.
- Container lifecycle management.
- Packaging and running Python applications using Docker.

## 🚀 What's Next?

- Docker Volumes and persistent storage.
- Docker Networks.
- Docker Compose.
- Multi-container applications.
- Containerizing FastAPI and PostgreSQL applications.

---

**Learning by building, experimenting, and documenting.**

*This is my first hands-on Docker learning project. More practical implementations will be added as I continue learning.*
