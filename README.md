#Description 

DevOps Project:
This is a project of CI CD using Jenkins, GitHub, SonarQube and Docker.
The project was about a simple website and I have used Nginx(docker conatiner) as the application hoster.

#INSTRUCTIONS

1. Created three ec2 instances from AWS
2. Installed Java & Jenkins on one, SonarQube on the other and finally docker on the last one.
3. Added sonarqube scanner in global tool config of jenkins to install automatically.
4. Added remote sonarQ server to jenkins(sonarQ server) provided the URL of SQ and access token created on sonarQ server for authentication.
5. Created a Freestyle project on Jenkins -> SCM from GitHub -> Webhooks for Build Trigger.
6. Added build step to execute sonarqube scanner with the analysis properties obtained from sonarqube server (used sonarqube scanner Plugin in Jenkins)
7. Added build steps to SCP(execute shell) all project files to remote docker server on a custom dir called website (used SSH2 Easy Plugin in Jenkins).
8. Added remote docker server to jenkins(server group center) and set up password authentication btwn the servers (ssh-keygen & ssh-copy-id)(etc/ssh/sshd_config).
9. Added build steps for remote commands on docker server-> cd into custom dir(website) and build a docker img and run a conatiner from there. 


RESULTS: 

#1. Code Quality Analysis by SonarQube server
      <img width="960" alt="image" src="https://github.com/Santhoshkumar1007/SiteDeploymentProject/assets/91725362/9306e520-3bc6-4ecc-b0df-300d1f44c569">


#2. Remote docker image build and container run part in Jenkins
      <img width="960" alt="image" src="https://github.com/Santhoshkumar1007/SiteDeploymentProject/assets/91725362/da9bb14d-4b9d-479d-af54-2f84221f73b9">



#3. Build Triggered by the Git push by webhooks machanism
      <img width="960" alt="image" src="https://github.com/Santhoshkumar1007/SiteDeploymentProject/assets/91725362/2c113d11-4571-441e-8f98-f241bb0039d9">


#4. Final Website running on the remote docker-server container
      <img width="960" alt="image" src="https://github.com/Santhoshkumar1007/SiteDeploymentProject/assets/91725362/f8bcb671-b334-4930-84ec-77a676f3e670">


