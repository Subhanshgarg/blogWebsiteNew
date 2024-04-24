---
title: "Docker on Webapplication"
date: 2024-04-24 19:24:00 +0800
categories: [Blogging, Tutorial]
tags: [Blogging,Docker,WebApplication,Flask]
---

# Introduction
This blog contains the steps  to deploy a web application using Docker. It also includes making images  and containers interact with each other. and also uploading those images to your docker hub.

# Steps:

## 1. Prepare Your Flask Application:
Ensure your Flask application is set up and working locally.
Create a Dockerfile in the root directory of your Flask application to define the Docker image for your Flask application.

## 2. Prepare Your MySQL Database:
If you haven't already, set up a MySQL database for your application.
Ensure you have a Dockerfile or a script to initialize your MySQL database with the necessary schema and data.

## 3. Create a Docker Compose File:
Create a docker-compose.yml file in the root directory of your project to define the services (Flask app and MySQL database) and their configurations.

## 4. Open a terminal or command prompt and navigate to the root directory of your project.
Build the Docker images using the following command:" docker-compose build "

## 5. Run Docker Containers:
Start the Docker containers using the following command: " docker-compose up "
This will start the Flask application and the MySQL database in separate containers.


## 6. Verify Your Application:
Open your web browser and navigate to http://localhost:5000 to verify that your Flask application is running.

## 7. Push Images to Docker Hub:
Log in to Docker Hub using the docker login command.
Tag your Docker images with your Docker Hub username and the repository name:
" docker tag <flask_image_name>:<tag> <dockerhub_username>/<repository_name>:<tag> "
" docker tag <mysql_image_name>:<tag> <dockerhub_username>/<repository_name>:<tag> "

Push the images to Docker Hub:
" docker push <dockerhub_username>/<repository_name>:<tag> "

Replace <flask_image_name> and <mysql_image_name> with the names of your Flask and MySQL images, <tag> with the tag you want to use, <dockerhub_username> with your Docker Hub username, and <repository_name> with the name of your repository on Docker Hub.

## 8. Deploy Your Application:
On the target server, install Docker and Docker Compose if they are not already installed.
Create a directory for your project and create a docker-compose.yml file with the same configuration as your local setup.
Pull the Docker images from Docker Hub using the docker-compose pull command.
Start the Docker containers using the docker-compose up command.

## 9. Done
Your Flask backend web application and MySQL database should now be deployed and running using Docker containers.

# MyWork:

Here are the images of the work i have done for the same:

![alt text](https://github.com/ManavRaval/myImages/blob/main/cloud_img1.png?raw=true)

![alt text](https://github.com/ManavRaval/myImages/blob/main/cloud_img2.png?raw=true)

![alt text](https://github.com/ManavRaval/myImages/blob/main/cloud_img3.png?raw=true)

            -- Thanks for reading. Feel free to reach me with any suggestions! 