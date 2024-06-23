# Jenkins-CI-CD-Pipeline
A Jenkins-based CI/CD pipeline demonstrating a Gitflow-inspired branching strategy, automated builds, tests, and Docker deployments.
# Jenkins-CI-CD-Pipeline

A Jenkins-based CI/CD pipeline demonstrating a Gitflow-inspired branching strategy, automated builds, tests, and Docker deployments.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Setup](#setup)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Welcome to the Jenkins-CI-CD-Pipeline repository! This project showcases a comprehensive CI/CD pipeline setup using Jenkins, following a Gitflow-inspired branching strategy. The repository includes:

- **Feature Branch Workflow**: Develop new features in dedicated branches.
- **Automated Builds**: Triggered on commits to feature, development, and main branches.
- **Continuous Testing**: Automated tests ensure code quality and functionality.
- **Deployment**: Docker images are built and pushed to Dockerhub upon merging into the main branch.

This setup ensures smooth and automated integration and delivery, enhancing productivity and maintaining high code quality.

## Features

- **Multibranch Pipeline**: Automatically manages Jenkins jobs for each branch.
- **Gitflow-inspired Branching Strategy**: Supports feature, development, and main branches.
- **Automated Builds and Tests**: Ensures code is built and tested with each commit.
- **Docker Integration**: Builds and pushes Docker images to Dockerhub.

## Setup

### Prerequisites

- Jenkins installed and configured.
- Jenkins plugins:
  - Multibranch Pipeline Plugin
  - Docker Pipeline Plugin
  - Git Plugin
- Docker installed and configured.
- A Git repository (e.g., GitHub).

### Steps

1. **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/Jenkins-CI-CD-Pipeline.git
    cd Jenkins-CI-CD-Pipeline
    ```

2. **Create branches:**

    ```bash
    git checkout -b development
    git push origin development
    git checkout -b feature/new-feature
    git push origin feature/new-feature
    ```

3. **Configure Jenkins:**

   - Create a new Multibranch Pipeline Job in Jenkins.
   - Set the repository URL.
   - Configure build triggers and scan intervals.

4. **Add credentials for Dockerhub in Jenkins:**

   - Go to Jenkins dashboard.
   - Manage Jenkins > Manage Credentials > (add Dockerhub credentials).

## Usage

### Developing a New Feature

1. **Create a new feature branch:**

    ```bash
    git checkout -b feature/your-feature
    ```

2. **Make changes and commit:**

    ```bash
    git add .
    git commit -m "Add new feature"
    git push origin feature/your-feature
    ```

3. **Merge feature branch into development branch:**

   - Create a pull request from `feature/your-feature` to `development` in your Git repository.
   - Merge the pull request.

4. **Merge development branch into main branch:**

   - Create a pull request from `development` to `main`.
   - Merge the pull request.

### Deployment

- When changes are merged into the `main` branch, the Jenkins pipeline will build a Docker image and push it to Dockerhub.

## Contributing

We welcome contributions! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make and commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Create a new Pull Request.

