# How to Install Jenkins on Docker
## Here's a step-by-step guide:
**Prerequisites:**
1. Docker installed: Ensure that Docker is installed on your system and running.
2. Docker Hub account (optional): If you plan to customize the Jenkins Docker image or publish your own, you'll need a Docker Hub account.
### Steps 
1. Run Jenkins using Docker:
Open your terminal and use the following command to run the Jenkins Docker container:
``` 
docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11
```
> `-p 8080:8080:` This maps port 8080 on your host machine to port 8080 inside the container, allowing you to access the Jenkins web interface.  
`-p 50000:50000:` This maps port 50000 on your host to port 50000 in the container, for potential Jenkins communication.  
`-v jenkins_home:/var/jenkins_home:` This creates a Docker volume named jenkins_home and mounts it to the /var/jenkins_home directory within the container, ensuring that Jenkins data is persistent.  
`jenkins/jenkins:lts-jdk11` : This specifies the Jenkins Docker image to use, with the LTS (Long-Term Support) version and JDK 11.   
2. Access Jenkins:
Open your web browser and navigate to http://localhost:8080. 
> You will be greeted with the Jenkins initial setup wizard. Follow the instructions to unlock Jenkins, install suggested plugins, and create the first administrator user. 
3. Running Jenkins as a service
> For persistent operation, consider running the Jenkins Docker container as a service. This ensures Jenkins starts automatically when the system restarts. 
4. Optional: Backing up Jenkins data:
You can easily back up Jenkins data by backing up the jenkins_home directory, as it contains all Jenkins configurations and plugins
