# 🚀 Collaborative Code Editor with Docker & AWS ECS

A production-ready collaborative code editor that enables multiple developers to edit code simultaneously in real time. The project demonstrates how modern real-time applications can be containerized and deployed efficiently on AWS using Docker, Amazon ECR, and Amazon ECS.

Unlike traditional development environments where frontend and backend are deployed separately, this project packages both into a single Docker image using a multi-stage build. This simplifies deployment, reduces infrastructure complexity, and provides a consistent runtime environment across local development and production.

---

## 📖 Problem Statement

Real-time collaborative applications require low-latency communication, conflict-free synchronization, and scalable deployment strategies. Deploying separate frontend and backend services also introduces additional operational complexity.

This project addresses these challenges by:

- Enabling multiple users to collaborate on the same code editor simultaneously.
- Synchronizing changes in real time using CRDTs.
- Managing user presence within collaborative sessions.
- Packaging the complete application into a single Docker image.
- Preparing the application for cloud-native deployment using Amazon ECS.

---

# ✨ Features

- 📝 Real-time collaborative code editing
- 👥 Live user presence tracking
- ⚡ Conflict-free synchronization using Yjs (CRDT)
- 🔄 WebSocket communication with Socket.IO
- 🎨 Monaco Editor integration
- ⚛️ React + Vite frontend
- 🚀 Express.js backend
- 🐳 Multi-stage Docker build
- ☁️ AWS ECR compatible Docker image
- 🚢 AWS ECS deployment ready
- ❤️ Health check endpoint for orchestration platforms

---

# 🏗️ System Architecture

```
                    +----------------------+
                    |      Web Browser     |
                    +----------+-----------+
                               |
                               |
                          HTTP/WebSocket
                               |
                               |
                    +----------v-----------+
                    |   Express Server     |
                    |    Socket.IO Server  |
                    +----------+-----------+
                               |
                 +-------------+-------------+
                 |                           |
          Static React App              Yjs Provider
                 |                           |
                 +-------------+-------------+
                               |
                      Real-Time Synchronization
                               |
                        Connected Users
```

---

# 🛠️ Tech Stack

### Frontend

- React
- Vite
- Monaco Editor
- Tailwind CSS

### Backend

- Node.js
- Express.js
- Socket.IO
- Yjs
- y-socket.io

### DevOps

- Docker
- Multi-stage Docker Builds
- Amazon ECR
- Amazon ECS

---

# 🐳 Docker Architecture

The project uses a **multi-stage Docker build**.

### Stage 1

- Copies the React application
- Installs dependencies
- Generates the production build

```
Frontend
    ↓
npm install
    ↓
npm run build
    ↓
dist/
```

### Stage 2

- Copies backend source
- Installs backend dependencies
- Copies the generated frontend build
- Starts the Express server

```
Backend
    ↓
npm install
    ↓
Copy dist/
    ↓
public/
    ↓
Node Server
```

Benefits:

- Smaller Docker image
- Faster deployments
- Single deployable artifact
- Production-ready build

---

# ☁️ AWS Deployment Flow

```
Developer
     │
     ▼
GitHub Repository
     │
     ▼
Docker Build
     │
     ▼
Docker Image
     │
     ▼
Amazon ECR
     │
     ▼
Amazon ECS
     │
     ▼
Running Container
     │
     ▼
Users Access Application
```

---

# 📂 Project Structure

```
Frontend
├── React
├── Monaco Editor
├── Yjs Integration
└── User Presence

Backend
├── Express Server
├── Socket.IO
├── Yjs Server
└── Health API

Docker
├── Multi-stage Build
└── Production Image
```

---

# 🚀 Getting Started

### Clone Repository

```bash
git clone <repository-url>
cd repository
```

### Build Docker Image

```bash
docker build -t collaborative-editor .
```

### Run Container

```bash
docker run -p 3000:3000 collaborative-editor
```

Open:

```
http://localhost:3000
```

---

# 🔍 Health Check

The application exposes a health endpoint for monitoring and container orchestration.

```
GET /health
```

Response

```json
{
    "message":"ok",
    "success":true
}
```

---

# 📚 Concepts Demonstrated

- Real-time collaborative applications
- CRDT (Conflict-free Replicated Data Types)
- WebSocket communication
- Multi-stage Docker builds
- Static asset serving through Express
- Containerized deployments
- Amazon ECR image registry
- Amazon ECS container orchestration
- Production-ready deployment workflow

---

# 📈 Future Improvements

- Authentication & Authorization
- Multiple collaborative rooms
- Persistent document storage
- Syntax highlighting for multiple languages
- Code execution
- File explorer
- Kubernetes deployment
- CI/CD with GitHub Actions
- HTTPS & Reverse Proxy using Nginx

---

# 🎯 Learning Outcomes

This project demonstrates both **software engineering** and **DevOps** concepts by combining modern frontend development, backend communication, real-time synchronization, containerization, and cloud deployment into a single production-ready application.# Prayatn
