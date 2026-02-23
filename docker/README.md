# Docker Multi-Container Application

## Overview
This project is a multi-container application using:

- Python Flask
- Redis
- Docker
- Docker Compose

## Application Routes
- / → Welcome message
- /count → Increments visit counter stored in Redis

## How to Run

docker compose up --build

Then visit:

http://localhost:5000
http://localhost:5000/count

## What I Learned
- Dockerfile creation
- Multi-container networking
- Service communication using docker-compose
- Redis as a key-value store

## Challenges
- Debugging Redis connection
- Understanding container networking
