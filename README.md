## CI/CD Pipeline with GitHub Actions & Docker
---
##  Project Overview
---
1. Builds a Docker image.
2. Runs tests.
3. Pushes the image to Docker Hub.
4. Deploys the app locally.

-----
##  Tools Used

- **GitHub**: Repository & CI/CD workflows
- **GitHub Actions**: CI/CD automation
- **Docker**: Containerization
- **Docker Hub**: Image repository
- **AWS EC2 / Minikube**: Local/VM deployment
- **Node.js & Express**: Sample application
----
##  Repository Structure
---
ci-cd-docker-demo/ <br>
│
├─ .github/ <br>
│ └─ workflows/ <br>
│ └─ docker-ci.yml # GitHub Actions CI/CD workflow <br>
├─ app.js # Sample Node.js app <br>
├─ package.json # Node.js dependenciesv <br>
├─ Dockerfile # Docker image definition <br>
├─ docker-compose.yml # Optional local deployment <br>
└─ README.md # Project documentation <br>
----
## ⚙️ Setup Instructions

### 1. Clone the Repo
bash
git clone https://github.com/<your-username>/ci-cd-docker-demo.git
cd ci-cd-docker-demo

----

## 3. GitHub Actions CI/CD

Workflow file: .github/workflows/docker-ci.yml

Triggers: push or pull_request on main branch

Steps:

1)Checkout code

2)Build Docker image

3)Login to Docker Hub

4)Push image to Docker Hub

5)Verify image

---

## Deploy on AWS EC2

sudo yum update -y
sudo amazon-linux-extras install docker -y
sudo service docker start
sudo usermod -aG docker ec2-user
newgrp docker

docker login -u <DOCKERHUB_USERNAME>
docker pull <DOCKERHUB_USERNAME>/ci-cd-demo:latest
docker run -d -p 80:3000 <DOCKERHUB_USERNAME>/ci-cd-demo:latest

# Open your browser at http://<EC2-Public-IP>.
---
## Screenshots
---
1)GitHub Repository workflow

![Branches](https://github.com/gawali-priyanka/ci-cd-docker-demo/blob/main/screenshorts/Github-repo-workflow.png?raw=true)

2)GitHub Actions Workflow

![Branches](https://github.com/gawali-priyanka/ci-cd-docker-demo/blob/main/screenshorts/Github-workflow.png?raw=true)

3)Docker Hub Image

![Branches](https://github.com/gawali-priyanka/ci-cd-docker-demo/blob/main/screenshorts/Dockerhub-image.png?raw=true)

4)Deployed App

![Branches](https://github.com/gawali-priyanka/ci-cd-docker-demo/blob/main/screenshorts/Deployment-application.png?raw=true)
