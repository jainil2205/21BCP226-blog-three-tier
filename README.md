# 21BCP226 - Three Tier Application

## Introduction to Three-Tier Application with MongoDB, Node.js, React.js, and Docker

A three-tier architecture divides an application into three logical layers: presentation layer, application layer, and data layer. In our case, we are using the following technologies:

- **MongoDB:** A NoSQL database used as the data layer to store and manage application data.
- **Node.js:** A JavaScript runtime environment used in the application layer to run server-side code.
- **React.js:** A JavaScript library used in the presentation layer to build interactive user interfaces.
- **Docker:** A containerization platform used to package the application along with its dependencies into containers for easy deployment and scalability.

## Steps to Deploy the Three-Tier Application

1. ### Get the Code from the required Repository

2. ### Build Docker Images

   Write Dockerfiles for frontend, backend, and MongoDB server. Then, build images for each component using Docker.

3. ### Run Docker Containers

   Run Docker containers using the built images for frontend, backend, and MongoDB server.

## Understanding Dockerfiles

A Dockerfile is a text file that contains instructions for building a Docker image. Here's a sample Dockerfile for each component:

- ### Frontend Dockerfile:

  ```Dockerfile
  FROM node:latest
  WORKDIR /app
  COPY package*.json ./
  RUN npm install
  COPY . .
  EXPOSE 3000
  CMD ["npm", "start"]
  ```

- ### Backend Dockerfile:

  ```Dockerfile
  FROM node:latest
  WORKDIR /app
  COPY package*.json ./
  RUN npm install
  COPY . .
  EXPOSE 5000
  CMD ["npm", "start"]
  ```

- ## Pushing Docker Images to Docker Hub
  Follow these steps to push Docker images to Docker Hub:

  ### Login to Docker Hub:
  ```bash
  docker login
  ```
  Enter your Docker Hub username and password when prompted.

  ### Tag the Docker Image:
  ```bash
  docker tag my-mongodb username/my-mongodb
  ```
  Replace username with your Docker Hub username.


  ### Push the Docker Image:
  ```bash
  docker push username/my-mongodb
  ```
  This will push the MongoDB Docker image to your Docker Hub repository.
