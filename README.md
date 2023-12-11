# Azure-Flask-App
In this individual Project 4, a **publicly accessible auto-scaling container using Azure App Services and Flask** has been implemented.

Project dependencies, program sep up steps, and data-driven recommendation has been demonstrated in README.md.


## Project Dependencies
- Platform:
  
  Azure (for App Deployment)
  
  Docker Hub(for docker image management)

  Codespace/VSCode (for Environment Setup)
  
- Libraries:

  Flask==2.3.3
  
  Python==3.10.8

  Docker

## Steps to Run the Programme
### Step1: Set up environment using GitHub Code Spaces/VScode

In this project, VSCode is used for local app development. Necessary packages are shown in requirement.txt.


### Step2: Build up Flask App on VSCode
- Build a basic flask app with the port number 1918 exposed.

![Dockerfile](images/Dockerfile.png)


- Build Docker File 
  - Build docker container with `sudo docker build -t kkapp .`
 
- Run the App
  - docker run `docker run -p 1918:1918 kkapp`
  - You can see the web rendering of the app at `http://127.0.0.1:1918`

   ![Webapp](images/webapp.png) 
    

### Step3: Login to DockerHub via Codespaces/VSCode
- Create a DockerHub repository on Dockerhub:

- log into docker hub on Codespace/VSCode and push the local docker image to remote docker hub repo:
  Commands are shown as below:
  - `docker login --username=lilinkekk`
  - `docker build -t lilinkekk/ids706_individualproject4_ll442 .`
  - `docker push lilinkekk/ids706_individualproject4_ll442`
 
  Local docker image is successfully deployed to docker hub as shown below
  ![Dockerhub](images/Dockerhub.png)

(Warning - Remember to create the repo before pushing!)

### Step4: Set up Azure Services 

- Log into Azure, search app services and select create (web app)

- When creating the app, select Docker Container

![Azure_dockercontainer](images/Azure_dockercontainer.png)

- When selecting the Docker container, point to the correct image tab.

![Azure_dockerhub](images/Azure_dockerhub.png)
![Azure_summary](images/Azure_summary.png)


- After deployment you'll need to go configuration and add "WEBSITES_PORT" with a value of 1918 (more below).

   This will allow your app to run on at the public URL provided by Azure.

  - Website Port 
![Azure_websiteport](images/Azure_websiteport.png)

  - Public URL
![Azure_url](images/Azure_url.png)
[ids706individualproject4.azurewebsites.net](https://ids706individualproject4.azurewebsites.net)


## Summary & Recommendations

### Project Summary

This project demonstrates a scalable Flask web application deployed on Azure App Services. It highlights efficient load handling and operational flexibility.

- Key Achievements
  
  - Auto-scaling Capability: Ensures optimal performance under varying load conditions.
    
  - Cloud-based Efficiency: Azure deployment offers high availability and reduces infrastructure overhead.
    
  - Cost-Effective Scalability: Auto-scaling minimizes operational costs, aligning resources with demand.
    
  - Improved User Experience: Consistent performance even during peak usage enhances user satisfaction.

### Recommendations

- Enhance Monitoring: Implement advanced monitoring tools for proactive performance management.

- Explore Additional Azure Services: Investigate Azure's other services, like Azure Functions, for potential enhancements.


## Video Demo
For more information about this project? [Press Me :D](https://youtu.be/PTc2jRxRrmU)
