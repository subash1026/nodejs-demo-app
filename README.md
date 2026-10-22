Node.js Demo Application — CI/CD Pipeline Setup

This repository contains a lightweight Node.js web application equipped with an automated CI/CD pipeline using Docker and GitHub Actions.

Project Overview
The goal of this project is to automate the entire software delivery process—from code commit to building and publishing container images to Docker Hub without manual intervention.

---
Architecture & Tools

* **Backend:** Node.js (Express)
* **Containerization:** Docker
* **Automation:** GitHub Actions
* **Registry:** Docker Hub

---
How the CI/CD Pipeline Works

The workflow is defined in `.github/workflows/main.yml`. Every time code is pushed to the `main` branch, the automated pipeline performs the following steps:

1. **Checkout:** Clones the repository inside the runner environment.
2. **Environment Setup:** Configures Node.js version 18.
3. **Test:** Installs dependencies and runs automated unit/integration tests (`npm test`).
4. **Authentication:** Authenticates into Docker Hub using encrypted repository secrets (`DOCKERHUB_USERNAME` & `DOCKERHUB_TOKEN`).
5. **Build & Publish:** Builds the Docker container image and pushes it to Docker Hub as `subash1026/nodejs-demo-app:latest`.

---
Running the Project Locally

1. Direct Node.js Run
```bash
# Install dependencies
npm install

# Run the app
npm start
