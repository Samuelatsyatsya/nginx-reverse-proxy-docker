# Rock Paper Scissors – Dockerized Full Stack Application

## Overview
This project is a full-stack Rock Paper Scissors game built with a modern web stack and containerized using Docker.

The application includes:
- A Node.js backend API that handles game logic
- A React frontend built with Vite
- Dockerfiles for both frontend and backend
- A Docker Compose configuration to run the application

---

## Tech Stack
- Frontend: React + Vite
- Backend: Node.js + Express
- Containerization: Docker
- Orchestration: Docker Compose

---

## Project Structure

rock-paper-scissors/
│
├── backend/
│ ├── Dockerfile
│ ├── package.json
│ ├── server.js
│
├── frontend/
│ ├── Dockerfile
│ ├── package.json
│ ├── vite.config.js
│ └── src/
│
├── docker-compose.yml
└── README.md


---

## How the Application Works
1. The user selects Rock, Paper, or Scissors in the frontend.
2. The frontend sends a request to the backend API.
3. The backend randomly selects a move for the computer.
4. The backend determines the game result (win, lose, or draw).
5. The result is returned and displayed in the frontend.

---

## Prerequisites
Make sure the following are installed:
- Docker Desktop or Docker Engine
- Docker Compose
- Node.js (optional, for local development)

---

## Running the Application with Docker

### Step 1: Clone the Repository
```bash
git clone https://github.com/Samuelatsyatsya/docker-node-lab.git
cd docker-node-lab
```

### Step 2: Build and Start the Containers
```bash
docker compose up --build
```

## This command builds the Docker images and starts both services.

### Step 3: Access the Application

Frontend: http://localhost:5173

Backend API: http://localhost:5000

## Docker Setup Details
### Backend Service

- Runs a Node.js Express server

- Exposes port 5000

- Contains the game logic

### Frontend Service

- Runs a React Vite development server

- Exposes port 5173

- Communicates with the backend through Docker Compose

### Useful Docker Commands

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

### Future Improvements

Add score tracking

Improve UI styling

Add environment variables

Create a production build using Nginx

Add automated tests

Expected Outcome

The application runs successfully in the browser, with the frontend and backend fully containerized and communicating through Docker Compose.



<p align="center">
  Made with ❤️ by Samuel
</p>