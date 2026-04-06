# ACEest Fitness & Gym — DevOps Assignment

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Flask](https://img.shields.io/badge/Flask-3.0.0-green)
![Docker](https://img.shields.io/badge/Docker-Enabled-blue)
![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-orange)
![Jenkins](https://img.shields.io/badge/Build-Jenkins-red)

## Project Overview
This project implements a fully automated CI/CD pipeline for ACEest Fitness & Gym management application. The application evolved from a tkinter desktop app through 10 versions into a Flask web API, demonstrating modern DevOps practices including version control, containerization, automated testing, and continuous deployment.

## Version History

| Version | File | Key Features |
|---------|------|-------------|
| v1.0 | Aceestver-1.0.py | MVP - Basic fitness program display |
| v1.1 | Aceestver-1.1.py | Expanded UI and program details |
| v1.1.2 | Aceestver1.1.2.py | Matplotlib charts and CSV export |
| v2.0.1 | Aceestver2.0.1.py | SQLite database introduced |
| v2.1.2 | Aceestver-2.1.2.py | Refined database schema |
| v2.2.1 | Aceestver-2.2.1.py | Charts integrated with database |
| v2.2.4 | Aceestver-2.2.4.py | Full client and workout management |
| v3.0.1 | Aceestver-3.0.1.py | Refactoring and code cleanup |
| v3.1.2 | Aceestver-3.1.2.py | Modularized with workout history |
| v3.2.4 | Aceestver-3.2.4.py | Login, PDF reports, AI programs |

## Tech Stack

| Technology | Purpose |
|------------|---------|
| Python 3.11 | Core application language |
| Flask 3.0.0 | Web API framework |
| SQLite | Local database |
| Pytest | Unit testing framework |
| Docker | Containerization |
| GitHub Actions | CI/CD pipeline automation |
| Jenkins | Build server and quality gate |

## Local Setup and Execution

### Prerequisites
- Python 3.11 or higher
- Docker Desktop
- Git

### Installation Steps

Step 1 - Clone the repository

    git clone https://github.com/2024tm93639-creator/aceest-devops.git
    cd aceest-devops

Step 2 - Install dependencies

    pip install -r requirements.txt

Step 3 - Run the application

    python app.py

Step 4 - Open your browser and go to

    http://localhost:5000

## Running Tests Manually

Step 1 - Install pytest

    pip install pytest

Step 2 - Run the test suite

    pytest test_app.py -v

Step 3 - Run with coverage report

    pytest test_app.py -v --tb=short

### Expected Output
- test_homepage_returns_200 PASSED
- test_programs_returns_three PASSED
- test_add_client_missing_name PASSED
- test_bmi_calculation PASSED

## Docker Setup

### Build the Docker Image

    docker build -t aceest-app .

### Run the Container

    docker run -p 5000:5000 aceest-app

### Verify Container is Running

    docker ps

### Open the Application

    http://localhost:5000

## CI/CD Pipeline Overview

### GitHub Actions
Every push or pull request to main branch automatically triggers the pipeline which executes the following stages:

- Stage 1 - Build and Lint: Installs dependencies and checks code for syntax errors using flake8
- Stage 2 - Docker Image Assembly: Builds the Docker container image
- Stage 3 - Automated Testing: Runs the full Pytest suite inside the containerized environment

### Jenkins Integration
Jenkins serves as a secondary validation layer and quality gate:

- Monitors GitHub repository for new commits
- Pulls latest code automatically on every push
- Performs a clean build of the environment
- Runs the test suite to confirm build integrity
- Reports pass or fail status of every build

### Pipeline Flow

    Developer pushes code
          |
          v
    GitHub Actions triggered
          |
          v
    Lint and Syntax Check
          |
          v
    Docker Image Built
          |
          v
    Pytest Suite Executed
          |
          v
    Jenkins Build Triggered
          |
          v
    Clean Build Validated
          |
          v
    Deployment Ready

## Project Structure

    aceest-devops/
    ├── app.py
    ├── test_app.py
    ├── requirements.txt
    ├── Dockerfile
    ├── README.md
    ├── .github/
    │   └── workflows/
    │       └── main.yml
    ├── Aceestver-1.0.py
    ├── Aceestver-1.1.py
    ├── Aceestver1.1.2.py
    ├── Aceestver2.0.1.py
    ├── Aceestver-2.1.2.py
    ├── Aceestver-2.2.1.py
    ├── Aceestver-2.2.4.py
    ├── Aceestver-3.0.1.py
    ├── Aceestver-3.1.2.py
    └── Aceestver-3.2.4.py

## Author
- **Name**: Upendra Agrawal
- **Course**: Introduction to DevOps (SEZG514)
- **Assignment**: Assignment 1 - Implementing Automated CI/CD Pipelines
- **Repository**: https://github.com/2024tm93639-creator/aceest-devops
