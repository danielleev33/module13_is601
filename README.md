# Module 13 - JWT Authentication, Front-End Login/Register, and CI/CD

## Overview

This project implements a JWT-based authentication system using FastAPI, Docker, PostgreSQL, and GitHub Actions. The application includes user registration and login functionality, front-end pages for authentication, automated tests, and a CI/CD workflow that builds, tests, scans, and deploys the Docker image to Docker Hub.

This module focuses specifically on authentication before adding the full BREAD calculation front-end in Module 14.

## Features

- FastAPI backend application
- JWT-based authentication
- User registration endpoint
- User login endpoint
- Password hashing
- Pydantic validation for user input
- HTML/CSS/JavaScript login and registration pages
- Client-side validation for forms
- Docker-based local development
- PostgreSQL database service through Docker Compose
- Automated testing with pytest
- End-to-end testing support
- GitHub Actions CI/CD pipeline
- Docker Hub deployment after successful workflow run
- Trivy security scan in CI/CD pipeline

## Tech Stack

| Tool | Purpose |
|---|---|
| FastAPI | Backend API framework |
| PostgreSQL | Database |
| SQLAlchemy | ORM/database interaction |
| Pydantic | Request and response validation |
| JWT | Token-based authentication |
| Docker | Containerized application environment |
| Docker Compose | Runs the app and database together |
| pytest | Automated testing |
| Playwright | End-to-end/browser testing support |
| GitHub Actions | CI/CD automation |
| Docker Hub | Stores deployed Docker images |
| Trivy | Security scanning |

## Project Structure

```text
module13_is601/
├── app/
│   ├── main.py
│   ├── models/
│   ├── routes/
│   ├── schemas/
│   ├── services/
│   └── database.py
├── static/
├── templates/
│   ├── login.html
│   └── register.html
├── tests/
│   ├── e2e/
│   ├── integration/
│   └── unit/
├── .github/
│   └── workflows/
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── README.md

## Running the Project Locally
- git clone git@github.com:danielleev33/module13_is601.git
- cd module13_is601

## Build the Docker Containers
- docker compose build --no-cache

## Start the application
- docker compose up -d

## Check That the App Is Running
- curl http://localhost:8000/health
- Expected response: {"status":"ok"}

## Open the Application in the Browser
http://localhost:8000/register
http://localhost:8000/login
http://localhost:8000/docs

## Running Tests Locally
- docker compose exec web pytest -p no:cov -o addopts='' -v
- Expected Result: 99 passed, 1 skipped

## Checking Installed Dependency Versions
- docker compose exec web python -m pip freeze | grep -E "cryptography|cffi|typing|h11|httpcore|python-multipart|fastapi|starlette"

## Docker Hub
- Docker Image: danielleev33/module13_is601

- Docker Hub Link: https://hub.docker.com/r/danielleev33/module13_is601