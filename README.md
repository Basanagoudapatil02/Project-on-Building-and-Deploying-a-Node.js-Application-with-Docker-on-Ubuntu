Building and Deploying a Node.js Application with Docker on Ubuntu

![image](https://user-images.githubusercontent.com/63364609/233578283-21cfc13a-7475-4509-b477-6a02bbef8be1.png)


Step 1 - Installation of docker on Ubuntu
The first step is to update the package manager. The second step is to install Docker by using the command "sudo apt-get install docker.io -y" on the terminal. After installation, the Docker version can be checked by typing "sudo docker –version" in the terminal.
Command-
1.	apt-get update
2.	apt-get install docker.io -y
3.	docker --version

![image](https://user-images.githubusercontent.com/63364609/233578312-0cd9f147-559e-44f7-8483-ca88b9cd648e.png)

![image](https://user-images.githubusercontent.com/63364609/233578333-eecf8886-ba78-4204-bb4c-f1637a24aee6.png)
 
Step 2 : Clone the code from Github
The code for the project is cloned from GitHub using the command 'git clone <repository_url>'. In this case, the repository URL is
https://github.com/LondheShubham153/node-todo-cicd.git
 
 ![image](https://user-images.githubusercontent.com/63364609/233578384-4fa7f2b1-4d12-4b5d-af3c-7f82942279a2.png)

(Here I’m cloning the code from Shubham londhe’s account and even you can forks that Repositorie to your github account).

Step 3: Check the files and understand the requirements
Check the files and understand the requirements Once the code has been cloned, we navigate to the directory using the command 'cd react_django_demo1_app' and use the 'ls' command to list the files in the directory. This helps us to understand the requirements of the project.
Commands
- Cd react_django_demo1_app
- ls

![image](https://user-images.githubusercontent.com/63364609/233578426-63418132-06df-4cb2-93cd-6f6f45cc60e2.png)

In the README.md file, the user can find the requirements for the project. After understanding 'README.md' file the requirements for the project are documented, including the need for Node.js, Java, and npm.  
 
![image](https://user-images.githubusercontent.com/63364609/233578447-c0dcccf9-e311-4ff7-b885-0d04d466c5d1.png)

Step 4: Create a docker image using a dockerfile

To Create a Docker image using a Dockerfile A Dockerfile is used to define the configuration of the Docker image. In this step, a Dockerfile is created to build the Docker image for the project.
I suggested to use base image the node image version 19-alpine3.16 from the Docker Hub. 
The Alpine Linux distribution is a lightweight Linux distribution that is commonly used in Docker images because of its small size. The 19-alpine3.16 tag refers to a specific version of the image.

![image](https://user-images.githubusercontent.com/63364609/233578493-287772f5-e9a6-46e3-a62f-095d6f18ab25.png)

Create a Dockerfile to define the environment for the application. The Dockerfile specifies the base image to use, the packages to install, and any other configuration required for the application.

![image](https://user-images.githubusercontent.com/63364609/233578528-59cc1a93-6990-49bc-876d-9212a4a4bcda.png)

Step 4: Build the docker image
Build the Docker image Once the Dockerfile has been created, the Docker image is built using the 'docker build' command. The '-t' flag is used to specify the name and tag of the Docker image.
Command
docker build . -t node-todo-app:latest

![image](https://user-images.githubusercontent.com/63364609/233578598-3e4dc017-2871-4324-8fd4-34d2b795c1e6.png)

![image](https://user-images.githubusercontent.com/63364609/233578636-fb05a5fe-37b5-4e78-a8b8-92e5dc2c654e.png)
 
To check the images, use the command "docker images".

![image](https://user-images.githubusercontent.com/63364609/233578656-1dafddf4-231f-4214-a1d8-fe74bceb3b1a.png)


Step 5: Create a docker container
Create a Docker container A Docker container is created using the Docker image that was built in the previous step. The '-d' flag is used to run the container in detached mode, and the '-p' flag is used to map port 8000 of the container to port 8000 of the host machine.

Commands
docker run -d -p8000:8000 node-todo-app:latest

![image](https://user-images.githubusercontent.com/63364609/233578689-5688e829-5bea-43d5-9fec-20dc9047ae94.png)

The user can check the running containers by using the command "sudo docker ps". 

![image](https://user-images.githubusercontent.com/63364609/233578711-cbcb6307-2f5b-4522-a097-2d0d88a66674.png)


Step 6: Open port 8000 in the instance’s security inbound rule
Open port 8000 in the instance’s security inbound rule To allow traffic to access the application, port 8000 needs to be opened in the instance’s security inbound rule.

![image](https://user-images.githubusercontent.com/63364609/233578735-03474522-d033-411f-a3d3-c3033f27613a.png)

Step 7: Check if the application is running
Check if the application is running Finally, we can check if the application is running by opening a browser and typing the URL 'http://<host_ip_address>:8000' in a web browser.

![image](https://user-images.githubusercontent.com/63364609/233578767-9a1c8fa1-2a26-4952-a085-ce0823d9c14e.png)







