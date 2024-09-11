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

docker-compose.yml
Location: Root directory of the project ( /docker-compose.yml)
Purpose: Defines how MongoDB is set up and connected. Specifies the image (mongo:latest), ports to expose, and volume to persist data. MongoDB itself does not require a separate Dockerfile or additional files for standard operations

![Screenshot (261)](https://github.com/user-attachments/assets/c826f8ce-104e-4dec-a9e1-6466ae9348b7)
![Screenshot (262)](https://github.com/user-attachments/assets/59e7fcee-2854-4712-b0a9-145c35227253)


## Execution Steps
### docker compose up -d

Purpose: docker-compose up -d starts Docker containers in detached mode, meaning they run in the background. In VSCode, this command builds and runs the services defined in docker-compose.yml file

![Screenshot (245)](https://github.com/user-attachments/assets/17a577a8-a853-417e-8867-34634adea3cf)

![Screenshot (248)](https://github.com/user-attachments/assets/26a8cb35-8155-4d9b-b2e9-ec6ff4bcee32)

![Screenshot (249)](https://github.com/user-attachments/assets/2a5354ae-01fe-4546-b6ea-e52af63c2662)

### _docker images_
This command will list all Docker images, showing the REPOSITORY, TAG, IMAGE ID, CREATED, and SIZE for each image.

![Screenshot (255)](https://github.com/user-attachments/assets/d8101bb1-361e-4711-bbf7-52e6ecc26743)

### _docker ps_
This command will display a list of active containers, including their CONTAINER ID, IMAGE, COMMAND, CREATED, STATUS, PORTS, and NAMES. To view all containers, including stopped ones

![Screenshot (256)](https://github.com/user-attachments/assets/5de22d8b-f0f8-4545-9079-674d401d9e53)

## Verify the Services
1. Frontend: Open your browser and navigate to http://localhost:5173 to access the React application.

![Screenshot (257)](https://github.com/user-attachments/assets/368bc1f2-e9f1-471c-b408-deb56bf33123)

2. MongoDB: Connect to MongoDB at mongodb http://localhost:27017 using a MongoDB client like MongoDB Compass.

![Screenshot (258)](https://github.com/user-attachments/assets/eab1da7b-b4ff-43fb-925b-0a733e665a4d)


## Services running on  Docker desktop  hub
Docker desktop Hub is a cloud-based repository where Docker users can store and share Docker images. It provides a vast collection of pre-built images for popular software, allowing you to easily pull and use them in your projects

![Screenshot (260)](https://github.com/user-attachments/assets/b34b95d8-acec-4e31-8bb9-e467aa1cc25c)

![Screenshot (259)](https://github.com/user-attachments/assets/a843c0a5-eb23-4db9-a220-09b28bd8d925)




















