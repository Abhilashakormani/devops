<<<<<<< HEAD
# devops
=======
# DevFlow
DevOps-Based Automated CI/CD Pipeline for Web Application Deployment

## 1. Project Overview
DevFlow is a beginner-friendly DevOps CBP project that demonstrates a simple automated CI/CD workflow for a static website. The project is intentionally lightweight so it is easy to explain during a college viva.

The website is a polished static landing page that visualizes the pipeline:

Developer -> GitHub -> GitHub Actions -> Build -> Test -> Docker -> Docker Hub -> Render -> Live Website

## 2. Objective
The main objective of this project is to reduce manual deployment effort and show how code can move from a local change to a live website through automation.

## 3. Features
- Modern static landing page with a professional DevOps design
- Sticky navigation with smooth scrolling
- Hero section with pipeline visualization
- CI/CD pipeline cards
- Demo pipeline status cards
- Beginner-friendly timeline explanation
- Technologies used section
- About section with simple wording
- Docker support for easy containerized deployment
- GitHub Actions workflow for validation, testing, Docker build, and Docker Hub push

## 4. Technologies Used
| Technology | Purpose |
| --- | --- |
| HTML | Page structure |
| CSS | Layout, design, and responsiveness |
| JavaScript | Navigation toggle and small UI interactions |
| Git | Version control |
| GitHub | Source code hosting |
| GitHub Actions | CI/CD automation |
| Docker | Container packaging |
| Docker Hub | Image registry |
| Render | Web hosting and deployment |

## 5. Project Architecture
```text
Developer
    ↓
Git
    ↓
GitHub
    ↓
GitHub Actions
    ↓
Build
    ↓
Automated Test
    ↓
Docker Build
    ↓
Docker Hub
    ↓
Render
    ↓
Live Web Application
```

## 6. Project Structure
```text
devops-cicd-project/
├── index.html
├── style.css
├── script.js
├── Dockerfile
├── .dockerignore
├── README.md
└── .github/
    └── workflows/
        └── ci-cd.yml
```

## 7. How the Website Works
- The navigation bar links to each section on the same page.
- The hero section introduces the project and the CI/CD idea.
- The pipeline section shows the main automation stages.
- The status section displays demo states such as SUCCESS and LIVE.
- The timeline section explains the workflow in simple steps.
- The technologies section lists the tools used in the project.
- The about section explains what the project is and why it matters.

## 8. Docker Setup
The project uses a simple Nginx container to serve the static files.

### Build the Docker image
```bash
docker build -t devflow .
```

### Run the container locally
```bash
docker run -p 8080:80 devflow
```

### Open the website
Open this URL in your browser:

```text
http://localhost:8080
```

### Stop the container
- Press `Ctrl + C` if the container is running in the foreground.
- If it is running in the background, use `docker ps` to find the container id and then run `docker stop <container-id>`.

## 9. GitHub Repository Setup
1. Create a new repository on GitHub.
2. Copy this project into the repository.
3. Push the files to the `main` branch.
4. Every future push to `main` will trigger GitHub Actions.

## 10. GitHub Actions Setup
The workflow file is located at [`.github/workflows/ci-cd.yml`](.github/workflows/ci-cd.yml).

It performs these steps:
- Checkout code
- Validate that the required files exist
- Run a simple automated test
- Build the Docker image
- Log in to Docker Hub using GitHub Secrets
- Push the Docker image to Docker Hub

## 11. Docker Hub Setup
1. Create an account on Docker Hub.
2. Create a repository named `devflow` or use a similar name.
3. Note your Docker Hub username.
4. GitHub Actions will push the image using the format:

```text
<DOCKERHUB_USERNAME>/devflow:latest
```

## 12. GitHub Secrets Setup
Add these secrets in your GitHub repository settings:

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`

### Why secrets are needed
Credentials should not be hardcoded in the repository because that would expose them publicly. GitHub Secrets keep the values protected.

### How to add secrets
1. Open the GitHub repository.
2. Go to **Settings**.
3. Open **Secrets and variables**.
4. Select **Actions**.
5. Add `DOCKERHUB_USERNAME` and `DOCKERHUB_TOKEN`.

## 13. Render Deployment
You can deploy the project on Render as a Docker-based web service.

### Basic steps
1. Create a Render account.
2. Create a new **Web Service**.
3. Connect the GitHub repository.
4. Choose the Docker environment or Docker-based deployment option.
5. Use the existing `Dockerfile` in the repository.
6. Deploy the service.
7. Copy the live Render URL after deployment finishes.

### Beginner-friendly note
Render can work directly with this Dockerfile, so you do not need a backend, database, or extra cloud service.

## 14. Complete CI/CD Workflow
1. Developer updates the website.
2. Code is committed with Git.
3. Code is pushed to GitHub.
4. GitHub Actions starts automatically.
5. The workflow validates the files.
6. A simple test checks that the important project files and content exist.
7. Docker builds the image.
8. The image is pushed to Docker Hub.
9. Render deploys the application.
10. The website goes live.

## 15. How to Run Locally
### Option 1: Open the file directly
Open `index.html` in a browser.

### Option 2: Use Docker
Follow the Docker steps above to run the site on `http://localhost:8080`.

## 16. How to Test Docker Locally
```bash
docker build -t devflow .
docker run -p 8080:80 devflow
```

Then open:

```text
http://localhost:8080
```

## 17. Expected CI/CD Flow
```text
Developer -> GitHub -> GitHub Actions -> Build -> Test -> Docker -> Docker Hub -> Render -> Live Website
```

## 18. Git Commands
### First-time setup
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <repository-url>
git push -u origin main
```

### Normal development workflow
```bash
git add .
git commit -m "Update website"
git push
```

Pushing code to the `main` branch triggers GitHub Actions automatically.

## 19. Future Enhancements
- Add real test automation for the website content
- Add a downloadable project report
- Add a presentation slide deck
- Add a small animated diagram for the pipeline
- Add a dark/light theme switch

## 20. Conclusion
DevFlow is a simple and professional DevOps CBP project that demonstrates automated CI/CD in a way that is easy to understand, easy to present, and easy to deploy.

## 21. Viva Questions and Answers
### 1. What is DevOps?
DevOps is a practice that combines development and operations to deliver software faster and more reliably.

### 2. What is CI?
CI stands for Continuous Integration. It means merging code changes frequently and validating them automatically.

### 3. What is CD?
CD stands for Continuous Delivery or Continuous Deployment. It means preparing or releasing software automatically.

### 4. What is CI/CD?
CI/CD is the automated process of integrating, testing, building, and deploying software.

### 5. Why GitHub Actions?
It automates the workflow whenever code is pushed to the repository.

### 6. What is Docker?
Docker is a tool that packages an application and its environment into a container.

### 7. Why use Docker?
It makes the application run consistently on different machines.

### 8. What is Docker Hub?
Docker Hub is a registry used to store and share Docker images.

### 9. What is Render?
Render is a platform used to host and deploy web applications.

### 10. What are GitHub Secrets?
They are protected values used in GitHub Actions for sensitive information.

### 11. Why should credentials not be hardcoded?
Hardcoded credentials can be exposed publicly and create security risks.

### 12. What happens when code is pushed?
GitHub Actions runs the workflow automatically.

### 13. What is the purpose of the Dockerfile?
It defines how the Docker image is built.

### 14. What is the difference between a Docker image and container?
An image is the packaged template, and a container is the running instance of that image.

### 15. What problem does this project solve?
It shows how a simple website can be built and deployed automatically with minimal manual work.# DevFlow
DevOps-Based Automated CI/CD Pipeline for Web Application Deployment

## 1. Project Overview
DevFlow is a beginner-friendly DevOps CBP project that demonstrates a simple automated CI/CD workflow for a static website. The project is intentionally lightweight so it is easy to explain during a college viva.

The website is a polished static landing page that visualizes the pipeline:

Developer -> GitHub -> GitHub Actions -> Build -> Test -> Docker -> Docker Hub -> Render -> Live Website

## 2. Objective
The main objective of this project is to reduce manual deployment effort and show how code can move from a local change to a live website through automation.

## 3. Features
- Modern static landing page with a professional DevOps design
- Sticky navigation with smooth scrolling
- Hero section with pipeline visualization
- CI/CD pipeline cards
- Demo pipeline status cards
- Beginner-friendly timeline explanation
- Technologies used section
- About section with simple wording
- Docker support for easy containerized deployment
- GitHub Actions workflow for validation, testing, Docker build, and Docker Hub push

## 4. Technologies Used
| Technology | Purpose |
| --- | --- |
| HTML | Page structure |
| CSS | Layout, design, and responsiveness |
| JavaScript | Navigation toggle and small UI interactions |
| Git | Version control |
| GitHub | Source code hosting |
| GitHub Actions | CI/CD automation |
| Docker | Container packaging |
| Docker Hub | Image registry |
| Render | Web hosting and deployment |

## 5. Project Architecture
```text
Developer
    ↓
Git
    ↓
GitHub
    ↓
GitHub Actions
    ↓
Build
    ↓
Automated Test
    ↓
Docker Build
    ↓
Docker Hub
    ↓
Render
    ↓
Live Web Application
```

## 6. Project Structure
```text
devops-cicd-project/
├── index.html
├── style.css
├── script.js
├── Dockerfile
├── .dockerignore
├── README.md
└── .github/
    └── workflows/
        └── ci-cd.yml
```

## 7. How the Website Works
- The navigation bar links to each section on the same page.
- The hero section introduces the project and the CI/CD idea.
- The pipeline section shows the main automation stages.
- The status section displays demo states such as SUCCESS and LIVE.
- The timeline section explains the workflow in simple steps.
- The technologies section lists the tools used in the project.
- The about section explains what the project is and why it matters.

## 8. Docker Setup
The project uses a simple Nginx container to serve the static files.

### Build the Docker image
```bash
docker build -t devflow .
```

### Run the container locally
```bash
docker run -p 8080:80 devflow
```

### Open the website
Open this URL in your browser:

```text
http://localhost:8080
```

### Stop the container
- Press `Ctrl + C` if the container is running in the foreground.
- If it is running in the background, use `docker ps` to find the container id and then run `docker stop <container-id>`.

## 9. GitHub Repository Setup
1. Create a new repository on GitHub.
2. Copy this project into the repository.
3. Push the files to the `main` branch.
4. Every future push to `main` will trigger GitHub Actions.

## 10. GitHub Actions Setup
The workflow file is located at [`.github/workflows/ci-cd.yml`](.github/workflows/ci-cd.yml).

It performs these steps:
- Checkout code
- Validate that the required files exist
- Run a simple automated test
- Build the Docker image
- Log in to Docker Hub using GitHub Secrets
- Push the Docker image to Docker Hub

## 11. Docker Hub Setup
1. Create an account on Docker Hub.
2. Create a repository named `devflow` or use a similar name.
3. Note your Docker Hub username.
4. GitHub Actions will push the image using the format:

```text
<DOCKERHUB_USERNAME>/devflow:latest
```

## 12. GitHub Secrets Setup
Add these secrets in your GitHub repository settings:

- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`

### Why secrets are needed
Credentials should not be hardcoded in the repository because that would expose them publicly. GitHub Secrets keep the values protected.

### How to add secrets
1. Open the GitHub repository.
2. Go to **Settings**.
3. Open **Secrets and variables**.
4. Select **Actions**.
5. Add `DOCKERHUB_USERNAME` and `DOCKERHUB_TOKEN`.

## 13. Render Deployment
You can deploy the project on Render as a Docker-based web service.

### Basic steps
1. Create a Render account.
2. Create a new **Web Service**.
3. Connect the GitHub repository.
4. Choose the Docker environment or Docker-based deployment option.
5. Use the existing `Dockerfile` in the repository.
6. Deploy the service.
7. Copy the live Render URL after deployment finishes.

### Beginner-friendly note
Render can work directly with this Dockerfile, so you do not need a backend, database, or extra cloud service.

## 14. Complete CI/CD Workflow
1. Developer updates the website.
2. Code is committed with Git.
3. Code is pushed to GitHub.
4. GitHub Actions starts automatically.
5. The workflow validates the files.
6. A simple test checks that the important project files and content exist.
7. Docker builds the image.
8. The image is pushed to Docker Hub.
9. Render deploys the application.
10. The website goes live.

## 15. How to Run Locally
### Option 1: Open the file directly
Open `index.html` in a browser.

### Option 2: Use Docker
Follow the Docker steps above to run the site on `http://localhost:8080`.

## 16. How to Test Docker Locally
```bash
docker build -t devflow .
docker run -p 8080:80 devflow
```

Then open:

```text
http://localhost:8080
```

## 17. Expected CI/CD Flow
```text
Developer -> GitHub -> GitHub Actions -> Build -> Test -> Docker -> Docker Hub -> Render -> Live Website
```

## 18. Git Commands
### First-time setup
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <repository-url>
git push -u origin main
```

### Normal development workflow
```bash
git add .
git commit -m "Update website"
git push
```

Pushing code to the `main` branch triggers GitHub Actions automatically.

## 19. Future Enhancements
- Add real test automation for the website content
- Add a downloadable project report
- Add a presentation slide deck
- Add a small animated diagram for the pipeline
- Add a dark/light theme switch

## 20. Conclusion
DevFlow is a simple and professional DevOps CBP project that demonstrates automated CI/CD in a way that is easy to understand, easy to present, and easy to deploy.

## 21. Viva Questions and Answers
### 1. What is DevOps?
DevOps is a practice that combines development and operations to deliver software faster and more reliably.

### 2. What is CI?
CI stands for Continuous Integration. It means merging code changes frequently and validating them automatically.

### 3. What is CD?
CD stands for Continuous Delivery or Continuous Deployment. It means preparing or releasing software automatically.

### 4. What is CI/CD?
CI/CD is the automated process of integrating, testing, building, and deploying software.

### 5. Why GitHub Actions?
It automates the workflow whenever code is pushed to the repository.

### 6. What is Docker?
Docker is a tool that packages an application and its environment into a container.

### 7. Why use Docker?
It makes the application run consistently on different machines.

### 8. What is Docker Hub?
Docker Hub is a registry used to store and share Docker images.

### 9. What is Render?
Render is a platform used to host and deploy web applications.

### 10. What are GitHub Secrets?
They are protected values used in GitHub Actions for sensitive information.

### 11. Why should credentials not be hardcoded?
Hardcoded credentials can be exposed publicly and create security risks.

### 12. What happens when code is pushed?
GitHub Actions runs the workflow automatically.

### 13. What is the purpose of the Dockerfile?
It defines how the Docker image is built.

### 14. What is the difference between a Docker image and container?
An image is the packaged template, and a container is the running instance of that image.

### 15. What problem does this project solve?
It shows how a simple website can be built and deployed automatically with minimal manual work.
>>>>>>> 586f3cf (Initial commit)
