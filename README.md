# CICD
step in brief

1.  Run the below commands to install Java and Jenkins
    Install Java
    
    sudo apt update <br>
    sudo apt install openjdk-17-jre
    Verify Java is Installed

    java -version
    
2. Now, you can proceed with installing Jenkins

    curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
      /usr/share/keyrings/jenkins-keyring.asc > /dev/null<br>
    echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
      https://pkg.jenkins.io/debian binary/ | sudo tee \
      /etc/apt/sources.list.d/jenkins.list > /dev/null<br>
    sudo apt-get update<br>
    sudo apt-get install jenkins<br>


3.  IN SG Inbound allow custom TCp 8080 or all traffic


4.  Login to Jenkins using the below URL:
    http://:8080 [You can get the ec2-instance-public-ip-address from your AWS EC2 console page]
    
5.   fter you login to Jenkins,
-Run the command to copy the Jenkins Admin Password - sudo cat /var/lib/jenkins/secrets/initialAdminPassword - Enter the Administrator password


6. Click on Install suggested plugins

Wait for the Jenkins to Install suggested plugins


7. Create First Admin User or Skip the step [If you want to use this Jenkins instance for future use-cases as well, better to create admin user]



8.  Jenkins Installation is Successful. You can now starting using the Jenkins


9. Install the Docker Pipeline plugin in Jenkins:
    Log in to Jenkins.
    Go to Manage Jenkins > Manage Plugins.
    In the Available tab, search for "Docker Pipeline".<br>
    Select the plugin and click the Install button.<br>
    Restart Jenkins after the plugin is installed.<br>
![image](https://github.com/user-attachments/assets/c5c528ff-a453-4276-910d-fb3f2d6e0c0b)


Wait for the Jenkins to be restarted.

**Docker Slave Configuration
**
Run the below command to Install Docker

sudo apt update<br>
sudo apt install docker.io<br>
Grant Jenkins user and Ubuntu user permission to docker deamon.<br>
sudo su - <br>
usermod -aG docker jenkins<br>
usermod -aG docker ubuntu<br>
systemctl restart docker<br>

9. Once you are done with the above steps, it is better to restart Jenkins.

http://<ec2-instance-public-ip>:8080/restart
The docker agent configuration is now successful.
