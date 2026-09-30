# CI/CD Pipeline using GitHub Actions, Docker and Docker Hub

## Project Overview

This project demonstrates a Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions, Docker, and Docker Hub.

The Python application is stored in a GitHub repository. Whenever changes are pushed to the `main` branch, GitHub Actions automatically builds the Docker image and pushes it to Docker Hub.

## Objective

The objective of this project is to:

- Create a Python application.
- Containerize the application using Docker.
- Configure a CI/CD workflow using GitHub Actions.
- Automatically build the Docker image.
- Push the Docker image to Docker Hub.
- Pull and run the Docker image locally.

## Technologies Used

- **Python**
- **Docker**
- **GitHub Actions**
- **Docker Hub**
- **GitHub**

## Project Structure

```text
github-actions-docker-project1/
│
├── .github/
│   └── workflows/
│       └── docker.yml
│
├── Dockerfile
├── app.py
├── requirements.txt
├── README.md
└── Minor_Project_4_CICD_Pipeline_Report (1).pdf
```

## Application

The application is a simple Python program that displays:

```text
Hello! CI/CD Pipeline using GitHub Actions and Docker
```

## Dockerfile

The Dockerfile uses Python 3.11 and creates a Docker image for the application.

```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

CMD ["python", "app.py"]
```

## GitHub Actions CI/CD Workflow

The workflow is stored at:

```text
.github/workflows/docker.yml
```

The workflow is triggered whenever code is pushed to the `main` branch.

### Workflow Steps

1. Checkout the GitHub repository.
2. Log in to Docker Hub using GitHub Secrets.
3. Build the Docker image.
4. Push the Docker image to Docker Hub.

### GitHub Secrets

The workflow uses the following repository secrets:

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

These secrets are used to authenticate with Docker Hub.

## Docker Hub Repository

The Docker image is pushed to:

```text
daliamahata/github-actions-docker-project:latest
```

## Docker Commands

### Pull the Docker Image

```bash
docker pull daliamahata/github-actions-docker-project:latest
```

### Run the Docker Container

```bash
docker run --rm daliamahata/github-actions-docker-project:latest
```

### Expected Output

```text
Hello! CI/CD Pipeline using GitHub Actions and Docker
```

## Validation

The project was validated by:

- Successfully running the GitHub Actions workflow.
- Successfully building the Docker image.
- Successfully pushing the Docker image to Docker Hub.
- Successfully pulling the image from Docker Hub.
- Successfully running the Docker image locally.
- Verifying the expected application output.

## Conclusion

This project demonstrates how GitHub Actions can be used to automate the Docker image build and deployment process. The Docker image is successfully pushed to Docker Hub and can be pulled and executed locally.

## Project Report

The complete project report is available in this repository:

`Minor_Project_4_CICD_Pipeline_Report (1).pdf`
