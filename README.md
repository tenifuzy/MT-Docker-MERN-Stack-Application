# A simple MERN stack application 
## Objective
This project sets up a MERN stack application using Docker and Docker Compose. The stack consists of a frontend built with React, a backend built with Node.js and Express, and a MongoDB database.

## Project Structure
1. /mern
2. /frontend       # React frontend application
3. /backend        # Node.js and Express backend application
4. /docker-compose.yml  # Docker Compose configuration file

##  Frontend Directory
1.  package.json
Location: /mern/frontend/package.json
Purpose: Manages frontend dependencies, scripts, and metadata. Lists libraries like React, React Router, etc., and contains scripts to run, build, and test the frontend

2. d. Dockerfile
Location: /mern/frontend/Dockerfile
Purpose: Defines how to build the Docker image for the frontend. Specifies the base image (e.g., Node.js), copies application files, installs dependencies, and sets up the build process

## Backend Directory
1. package.json
Location: /mern/backend/package.json
Purpose: Manages backend dependencies, scripts, and metadata. Lists libraries and contains scripts to start, test, and build the backend.

2. Dockerfile
Location: /mern/backend/Dockerfile
Purpose: Defines how to build the Docker image for the backend. Specifies the base image, copies application files, installs dependencies, and sets up the start command.

## Step

### Configuration of docker-compose.yml
``` docker-compose,yml
---
services:
  frontend:
    build: /mern/frontend
    container_name: frontend
    ports:
      - "5173:5173"  
    networks:
      - mtvpc

  backend:
    build: ./mern/backend
    container_name: backend
    ports:
      - "8000:8000" 
    environment:
      - MONGODB_URI=mongodb://mongo:27017/merndb
    networks:
      - mtvpc
    depends_on:
      - mongo

  mongo:
    image: mongo:latest  
    container_name: mongo
    ports:
      - "27017:27017"  
    networks:
      - mtvpc
    volumes:
      - mongo-data:/data/db  

networks:
  mtvpc:
    driver: bridge

volumes:
  mongo-data:
    driver: local  # Persist MongoDB data locally
'''























### Create a network for the docker containers

`docker network create demo`

### Build the client 

```sh
cd mern/frontend
docker build -t mern-frontend .
```

### Run the client

`docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend`

### Verify the client is running

Open your browser and type `http://localhost:5173`

### Run the mongodb container

`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

### Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```

### Run the server

`docker run --name=backend --network=demo -d -p 8000:8000 mern-backend`

## Using Docker Compose

`docker compose up -d`

