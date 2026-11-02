# Hill Runner - Automated CI/CD Pipeline using Jenkins, Docker & AWS EC2

## Project Overview

This project demonstrates an automated CI/CD pipeline for deploying a browser-based game called **Hill Runner** using Jenkins, Docker, GitHub, and AWS EC2.

Hill Runner is an endless running game developed using HTML, CSS, and JavaScript. Players navigate through hilly terrain, jump over obstacles, collect coins, and achieve high scores.

The application is containerized using Docker and served through an Nginx web server. Jenkins is used to automate the build and deployment workflow.

The project aims to demonstrate how DevOps tools can be integrated to simplify application deployment and reduce manual effort.

---

## Technologies Used

- **HTML5** - Web page structure
- **CSS3** - Styling and responsive design
- **JavaScript** - Game logic and interactions
- **HTML5 Canvas** - Game rendering
- **Git & GitHub** - Version control and source code management
- **Jenkins** - CI/CD pipeline automation
- **Docker** - Application containerization
- **Nginx** - Web server
- **AWS EC2** - Cloud hosting environment
- **GitHub Webhooks** - Automated pipeline triggering
- **Amazon Linux 2023** - Operating system

---

## Project Structure

```text
capstone-project/
│
├── screenshots/
│   ├── github-repo.jpg
│   ├── jenkins-dashboard.jpg
│   ├── jenkins-success.jpg
│   ├── webhook.jpg
│   ├── website.jpg
│   └── docker-ps.jpg
│
├── Dockerfile
├── index.html
├── Jenkinsfile
└── README.md
```

---

## Project Architecture

The project follows a CI/CD workflow in which source code is managed through GitHub and the deployment process is automated using Jenkins and Docker.

```text
Developer
    |
    v
GitHub Repository
    |
    v
GitHub Webhook
    |
    v
Jenkins Pipeline
    |
    v
Source Code Checkout
    |
    v
Docker Image Build
    |
    v
Container Deployment
    |
    v
AWS EC2 Environment
    |
    v
Hill Runner Game
```

---

## Application Features

Hill Runner includes the following features:

- Endless running gameplay.
- Player jumping and double-jump mechanics.
- Coin collection and score tracking.
- Obstacles and power-ups.
- High-score tracking.
- Sound effects and background music.
- Interactive game controls.
- Responsive game interface.

---

## Docker Configuration

Docker is used to containerize the Hill Runner application.

The Dockerfile uses Nginx as the base image to serve the static website.

### Dockerfile

```dockerfile
FROM nginx:1.28-alpine

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80
```

### Docker Configuration Explanation

- **FROM:** Specifies the Nginx base image.
- **COPY:** Copies the HTML file into the default Nginx web directory.
- **EXPOSE:** Documents port 80 as the container's intended web server port.

---

## Jenkins Pipeline

The Jenkins pipeline automates the application deployment process through three main stages.

### 1. Clone Repository

Jenkins retrieves the latest source code from the configured GitHub repository.

### 2. Build Docker Image

Jenkins executes the Docker build command to create an application image using the Dockerfile.

```bash
docker build -t capstone-web