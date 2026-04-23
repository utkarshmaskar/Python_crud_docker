# Flask MySQL CRUD App — Dockerized

A student management CRUD app built with Python Flask and MySQL, 
fully containerized using Docker and Docker Compose.

## How to Run

git clone your_repo_url
cd flask-docker-crud
docker compose up --build

Access at: http://localhost:5001

## What I Did
- Wrote Dockerfile for Flask app
- Wrote docker-compose.yml wiring Flask + MySQL
- Created MySQL volume for data persistence
- Fixed networking between containers
- Deployed locally using Docker Compose

## Tech Stack
- Python Flask
- MySQL 8.0
- Docker
- Docker Compose# Python Flask CRUD App

- Key Lessons

Dockerfile → builds your custom app image
docker-compose.yml → wires everything together
Containers talk using service names not localhost
Flask must run on 0.0.0.0 to be accessible outside container
Always use --build after code changes
Use down -v to wipe volumes and start MySQL fresh
Port conflicts on Mac — ControlCenter owns 5000, use 5001
