# CI/CD Pipeline with Docker, Jenkins, and GitHub

This repository showcases a Continuous Integration/Continuous Deployment (CI/CD) pipeline setup using Docker, Jenkins, and GitHub. The pipeline is tailored to streamline the automation of building, testing, and deploying Node.js applications, ensuring a robust and efficient development workflow.

## Overview

The CI/CD pipeline involves the following steps:

1. **GitHub Code Push**: The process is initiated when changes are pushed to the GitHub repository, triggering the pipeline.
2. **Jenkins Build Automation**: Jenkins, my go-to automation server, is configured to monitor the repository for new commits. Upon detecting changes, Jenkins kicks off the build process.
3. **Docker Image Construction**: Jenkins uses a base Docker image from DockerHub to build a new Docker image that encapsulates the  application and its dependencies.
4. **Docker Image Deployment**: After the Docker image is built, it is automatically pushed to my DockerHub repository, ready for deployment.
5. **Build Status Update**: Jenkins updates the build status on GitHub, providing real-time feedback on the CI/CD process.
6. **Build Notifications**: Notifications about the build status are sent via GitHub, keeping the team informed.

## Getting Started

To set up the CI/CD pipeline in your environment, follow these steps:

1. **Clone Repository**: Clone this repository to your local machine using the following command:
   ```
   git clone https://github.com/akithawijesinghe/CI-CD-Pipeline-Github-Docker-Jenkins
   ```
2. **Jenkins Configuration**: Set up Jenkins on your server. Ensure it monitors the GitHub repository for changes and installs necessary plugins like the Docker Pipeline Plugin.
3. **DockerHub Setup**: Make sure you have a DockerHub account where Jenkins can push Docker images.
4. **Pipeline Setup in Jenkins**: In Jenkins, create a new pipeline job and point it to the provided Jenkinsfile in this repository.
5. **Trigger the Build**: Start the CI/CD pipeline by either manually triggering a build in Jenkins or pushing a code change to the repository.

## Prerequisites
To run this CI/CD pipeline, you will need:

- A GitHub account for code versioning.
- Docker Desktop installed locally.
- A DockerHub account to store Docker images.
- A Jenkins server set up for CI/CD.
- Docker installed on your Jenkins server.





