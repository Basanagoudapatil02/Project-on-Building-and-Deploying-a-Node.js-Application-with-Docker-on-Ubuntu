Building and Deploying a Node.js Application with Docker on Ubuntu

![image](https://user-images.githubusercontent.com/63364609/233578283-21cfc13a-7475-4509-b477-6a02bbef8be1.png)  ![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/215c4c48-157d-4584-9874-3993731fab1a)



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



**Project on Building and Deploying a Node.js Application with Docker on Ubuntu using Jenkins CI/CD Pipeline
**

![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/5db862ce-b118-4d28-a426-2a2ae7e193cd)
 
The project aims to set up a Jenkins cluster consisting of a master node, an agent node, and a live server using three AWS EC2 instances. The project requires installing Java, Jenkins, and Docker on the master and agent nodes. The Jenkins cluster distributes the workload across multiple nodes, and the master node controls and assigns jobs to agent nodes. A pipeline is created to deploy a Node.js application using Docker. The pipeline has stages such as checkout, build, test, push, and deploy, which perform different tasks such as fetching source code from GitHub, building a Docker image, testing the image, pushing it to DockerHub, and deploying it to the live server. The project helps in automating the deployment process and saves time and effort by eliminating manual tasks.

Pre-Requisites:
1.	3 EC2 Instance (1 for Jenkins Master-Node, 1 for Jenkins Agent-Node and 1 for Deploying live sever)
2.	Jenkins and Java Installation in Master-Node
3.	Only Java Installation in Agent-Node
4.	Docker Installation

![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/5ddf8a39-5ed9-48fb-93f3-b2befc763755)
 

Step 1: Set up a Jenkins Cluster (Master Node and Agent Node) 
•	Jenkins can be configured as a single server or as a cluster of servers, where the workload is distributed across multiple nodes.
•	In a Jenkins cluster, multiple Jenkins instances, called nodes, work together to execute jobs. Each node has its own resources (such as CPU, memory, and disk space) and can perform builds independently.
•	The Jenkins master controls the cluster and assigns jobs to the agent nodes based on their availability and workload.
•	When a job is submitted to the Jenkins master, it decides which node to run the job on, based on the configured load balancing algorithm. The job is then executed on the selected node.
•	Refer this link to setup a agent node to master node https://medium.com/@basanagouda/setting-up-jenkins-cluster-master-node-and-agent-node-588cab83ce29
•	Here I have successfully connected agent node to master node and its online. 

![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/1a44992a-c9c4-486c-b102-75f60ba510c9)


Step 2: Create a Node-todo-app-deployment  Job with Pipeline
•	Go to Dashboard and click on New Item 
•	Enter an item name as “node-todo-app-deployment” and select pipeline as a job and click on OK.

![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/55e003be-90ba-4037-9093-84e94a1d5981)

 
•	Give job description
•	Select GitHub project and past GitHub project link
•	Here, I used my GitHub project link 

https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu.git

![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/13fff889-c744-4904-8030-42f4392a6722)


•	Selected GitHub hook trigger for GITscm polling for Build Triggers. To set-up webhook trigger follow the steps
•	Go to github project link in that go to setting of the project.
•	In setting, click on webhooks and click on add webhook
•	In Payload URL — entre https://<public ip of masternode>:8080/github-webhook/
•	In event you can select as your requirement.
•	Click on Add webhook

 ![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/5184d2cd-acf7-4fe3-982d-c02b6a6c9fad)

![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/d211be90-730a-461f-840e-a52de892d9d6)

 
•	In Pipeline definition, select pipeline script, enter your groovy code.

In a Jenkins pipeline, Groovy code is typically defined in a Jenkinsfile, which is a text file that contains the pipeline definition.The Jenkinsfile is written using the Groovy programming language and is used to define the stages, steps, and other elements of the pipeline.

There are many stages like Checkout, Build, Test, Push and Deploy

1.	Checkout Stage 
In a Jenkins pipeline, the "checkout" stage is used to fetch the source code from a version control system (VCS) such as Git, Subversion, or Mercurial.
In Pipeline, in agent section we have to mention our agent node name like Dev-Agent node.
pipeline {
    	agent { label 'Dev-Agent node' }
    	stages{
        	stage('Checkout'){
            	steps{
git url: 'https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu.git', branch: 'master' 
            	}
        }
2.	Build Stage 
In a Jenkins pipeline, the "Build" stage is typically the first stage in the pipeline, and it is responsible for building the source code.
The "Build" stage can include any necessary steps to compile the code, package it into a deployable format, and perform any other necessary preparation tasks.
Here in this stage, I am building a docker image using docker file through command and tagging image with basanagoudapatil/nodo-todo-app-test:latest'
Note: Install docker and docker compose in Jenkins Master-Node.
        stage('Build’){
            steps{
                sh 'docker build . -t basanagoudapatil/nodo-todo-app-test:latest'
            }
        }

3.	Test Stage
In a Jenkins pipeline, the "Test" stage is typically the second stage in the pipeline, and it is responsible for running tests to verify the correctness of the built code.
The "Test" stage can include any necessary steps to execute the tests and generate test reports.
Here in this stage, I am testing docker image by executing command 
docker inspect --type=image basanagoudapatil/nodo-todo-app-test:latest
        stage('Test image') {
            steps {
                echo 'testing...'
                sh 'docker inspect --type=image basanagoudapatil/nodo-todo-app-test:latest '
            }
        }
4.	Push Stage
In this stage, I am pushing docker image to my Dockerhub public repository and for dockerHub password I have generated separated dockerhub token. 
           stage('Push'){
     steps{
        	     sh "sudo docker login -u basanagoudapatil -p dckr_pat_OvN0lH_USJztUCkm0opyjz-yXNc"
                   sh 'sudo docker push basanagoudapatil/nodo-todo-app-test:latest'
            }
    }  
5.	Deploy Stage
In a Jenkins pipeline, the "Deploy" stage is typically the final stage in the pipeline, and it is responsible for deploying the built and tested artifacts to a target environment.
The "Deploy" stage can include any necessary steps to deploy the built artifacts to a target environment, such as a production server or a container registry.
Here in this stage, I am building docker compose and deploying to another server using SSH command.
        stage('Deploy'){
            steps{
                echo 'deploying on another server'
                sh 'sudo docker stop nodetodoapp || true'
                sh 'sudo docker rm nodetodoapp || true'
                sh 'sudo docker run -d --name nodetodoapp -p 8000:8000 basanagoudapatil/nodo-todo-app-test:latest'
                sh '''
                ssh -i Ubuntudemo.pem -o StrictHostKeyChecking=no ubuntu@44.211.144.201 <<EOF
                sudo docker login -u basanagoudapatil -p dckr_pat_OvN0lH_USJztUCkm0opyjz-yXNc
                sudo docker pull basanagoudapatil/nodo-todo-app-test:latest
                sudo docker stop nodetodoapp || true
                sudo docker rm nodetodoapp || true 
                sudo docker run -d --name nodetodoapp -p 8000:8000 basanagoudapatil/nodo-todo-app-test:latest
                '''
            }
        }

Final pipeline script
pipeline {
    agent { label 'Dev-Agent node' }
    
    stages{
        stage('Checkout'){
            steps{
                git url: 'https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu.git', branch: 'master'
            }
        }
        stage('Build'){
            steps{
                sh 'sudo docker build . -t basanagoudapatil/nodo-todo-app-test:latest'
            }
        }
        stage('Test image') {
            steps {
                echo 'testing...'
                sh 'sudo docker inspect --type=image basanagoudapatil/nodo-todo-app-test:latest '
            }
        }
        
        stage('Push'){
            steps{
        	     sh "sudo docker login -u basanagoudapatil -p dckr_pat_OvN0lH_USJztUCkm0opyjz-yXNc"
                 sh 'sudo docker push basanagoudapatil/nodo-todo-app-test:latest'
            }
        }  
        stage('Deploy'){
            steps{
                echo 'deploying on another server'
                sh 'sudo docker stop nodetodoapp || true'
                sh 'sudo docker rm nodetodoapp || true'
                sh 'sudo docker run -d --name nodetodoapp -p 80:80  basanagoudapatil/nodo-todo-app-test:latest'
                sh '''
                ssh -i Ubuntudemo.pem -o StrictHostKeyChecking=no ubuntu@44.211.144.201 <<EOF
                sudo docker login -u basanagoudapatil -p dckr_pat_OvN0lH_USJztUCkm0opyjz-yXNc
                sudo docker pull basanagoudapatil/nodo-todo-app-test:latest
                sudo docker stop nodetodoapp || true
                sudo docker rm nodetodoapp || true 
                sudo docker run -d --name nodetodoapp -p 8000:8000 basanagoudapatil/nodo-todo-app-test:latest
                '''
            }
        }
    }
}

 ![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/e2f193fa-0921-400d-919c-2def93619ce1)

 
•	Click on Save and Apply 
 
![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/e1e644d9-081d-4a7a-a70f-2bca0cc4a7f2)

 ![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/42394717-0066-42ae-bdbc-72c628dd7daa)

•	Finally…! Our Nodo-todo-app-deployment pipeline successfully Checkout, Build, Tested, Pushed and deployed.

•	Docker images successfully pushed to dockerHub repository

![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/45e6c8b5-355c-4c31-b982-362e7a9524f9)
 

Step 3: Open port 8000 in the Deploying on live server Instance’s security inbound rule
 
![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/a00eb70c-e661-41e3-8106-ad767ef477fb)

Open port 8000 in the instance’s security inbound rule To allow traffic to access the application, port 8000 needs to be opened in the instance’s security inbound rule.
 
![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/f628dcaa-6639-4c74-a175-33509d32f219)

Step 4: Check if the application is running
Check if the application is running Finally, we can check if the application is running by opening a browser and typing the URL ‘http://<live server instance public_ip_address>:8000’  (http://44.211.144.201) in a web browser.

 ![image](https://github.com/Basanagoudapatil02/Project-on-Building-and-Deploying-a-Node.js-Application-with-Docker-on-Ubuntu/assets/63364609/4d185ed3-9aa3-4fb5-81e7-6d69d5d08616)
 



 







