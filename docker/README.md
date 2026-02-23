# Docker Multi-Container Flask + Redis Application

## 📌 Project Overview

This project demonstrates a multi-container application using Docker and Docker Compose.

The application consists of:

- A Python Flask web application
- A Redis database used as a key-value store
- Dockerised services running inside isolated containers
- Container networking using Docker Compose

The goal of this project was to gain hands-on experience with container orchestration, service communication, and infrastructure containerisation.

---

## 🏗 Architecture

The system follows a simple multi-container architecture:

- Flask application container → Handles web requests
- Redis container → Stores visit counter data
- Docker Compose → Manages container orchestration and networking

The Flask application communicates with Redis using the service name defined inside docker-compose.

---

## ⚙️ Technologies Used

- Python
- Flask Framework
- Redis Database
- Docker
- Docker Compose

---

## 📡 Application Routes

### `/`
Returns a welcome message confirming the application is running.

### `/count`
Increments and displays the number of visits stored inside Redis.

Each request updates the counter value stored in the Redis key-value store.

---

## 🚀 How to Run the Project

Make sure you have Docker installed.

Then run the following command inside the project directory:

```bash
docker compose up --build
- Understanding container networking
