# Dockerized Full Stack Application with Nginx Reverse Proxy

## Overview
This project demonstrates how to containerize a full-stack web application and set up an **Nginx reverse proxy** to route traffic to the frontend and backend.

The application includes:
- A Node.js backend API (Express)  
- A React frontend built with Vite  
- A MySQL database  
- Nginx configured as a reverse proxy  
- Dockerfiles for frontend, backend, and Nginx  
- Docker Compose configuration for orchestration  

---

## Tech Stack
- Frontend: React + Vite  
- Backend: Node.js + Express  
- Database: MySQL  
- Reverse Proxy: Nginx  
- Containerization: Docker + Docker Compose  

---

## Project Structure

nginx-reverse-proxy-docker/
│
├── backend/
│ ├── Dockerfile
│ ├── package.json
│ ├── src/
│ └── server.js
│
├── frontend/
│ ├── Dockerfile
│ ├── package.json
│ ├── vite.config.js
│ └── src/
│
├── nginx/
│ └── nginx.conf
│
├── docker-compose.yml
└── .env


---

## How the Application Works
1. A user accesses the frontend via `http://localhost`.  
2. Nginx serves the React frontend and routes requests to `/api` to the backend.  
3. The backend communicates with the MySQL database to fetch or store data.  
4. The response is sent back to the frontend and displayed to the user.  

---

## Prerequisites
Make sure the following are installed:
- Docker Desktop or Docker Engine  
- Docker Compose  
- Node.js (optional, for local development)  

---

## Running the Application with Docker

#### Step 1: Clone the Repository
```bash
git clone https://github.com/Samuelatsyatsya/nginx-reverse-proxy-docker.git
cd nginx-reverse-proxy-docker
```

#### Step 2: Set Environment Variables

Create a .env file in the project root:

MYSQL_ROOT_PASSWORD=
MYSQL_DATABASE=
MYSQL_USER=
MYSQL_PASSWORD=

DB_HOST=
DB_PORT=

BACKEND_PORT=
FRONTEND_PORT=
NODE_ENV=
VITE_API_URL=

#### Step 3: Build and Start the Containers
```bash
docker compose up --build
```
This command builds the Docker images and starts all services: MySQL, backend, frontend, and Nginx.

#### Step 4: Access the Application

- Frontend: http://localhost

- Backend API: http://localhost/api

## Docker Setup Details
#### Backend Service

- Runs a Node.js Express server

- Exposes port 5000 inside the Docker network

- Handles API requests at /api

#### Frontend Service

- Builds the React Vite application

- Served by Nginx in the container

- Exposed on port 80

#### Nginx Reverse Proxy

- Listens on port 9000

- Serves frontend static files

- Proxies /api requests to the backend

#### MySQL Database

- Runs in a separate container

- Accessible to the backend via Docker network

## Useful Docker Commands

Stop the application:
```bash
docker compose down
```

Rebuild and restart containers:
```bash
docker compose up --build
```

List running containers:
```bash
docker ps
```

Check logs for a container:
```bash
docker logs <container_name>
```

## Future Improvements

- Add HTTPS using Nginx and Let's Encrypt

- Add environment variable secrets for production

- Enable logging and monitoring for all services

- Implement automated testing

<p align="center"> Made with ❤️ by Samuel </p>