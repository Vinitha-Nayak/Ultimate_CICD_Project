1. Launch a EC2 instance
2. Update the the server
   
     ```sudo apt update```

3.Clone the github repository

      ``` git clone  https://github.com/Vinitha-Nayak/Ultimate_CICD_Project.git```

4. Navigate to the folder

      ```cd Ultimate_CICD_Project```

5. Install Java

     ```sudo apt install openjdk-11-jre```

6.Verify Java installation

```java -version```

7.Install Jenkins
`curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins -y `

8. Check Jenkins installation
`ps -ef | grep jenkins`

9. Login to the jenkins
https://<ipaddress>:8080

10. Extract the password from this path
`sudo cat /var/lib/jenkins/secrets/initialAdminPassword`

11.Select Install suggested plugins

12. Create username, password , email

13. Now start using Jenkins

14. Create a new job > Give the name for your project > choose Pipleline > create job

15.Select `pipline script from scm' > choose scm `git` > Provide the github repository URL > Specify the branch > Specify the `Jenkinsfile` path

16. Install docker

`sudo apt install docker.io`

17. Grant permission

`sudo su - 
usermod -aG docker jenkins
usermod -aG docker ubuntu
systemctl restart docker`

18.Go to jenkins > `Manage Jenkins` > `plugins` > `Available plugins` > choose Docker Pipeline to install the plugin

19. Restart the jenkins

`http://<ec2-instance-public-ip>:8080/restart`

20. Add the Credentials for Docker and Github

    Dashboard > Manage Jenkins > Credentials > System > Global credentials (unrestricted)
       Add `Username` `password` `id`

    Dashboard > Manage Jenkins > Credentials > System > Global credentials (unrestricted) > choose secret text
       specify `secret` id

21. Build Now

    
    





