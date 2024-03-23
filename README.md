#Description 

DevOps Project:
This is a project of CI CD using Jenkins, GitHub, SonarQube and Docker.
The project was about a simple website and I have used Nginx(docker conatiner) as the application hoster.

#INSTRUCTIONS

1. Created three ec2 instances from AWS
2. Installed Java & Jenkins on one, SonarQube on the other and finally docker on the last one.
3. Created a Freestyle project on Jenkins -> SCM from GitHub -> Webhooks for Build Trigger
4. Added build steps to SCP(execute shell) all project files to remote docker server on a custom dir called website (used SSH2 Easy Plugin in Jenkins)
5. Added remote docker server to jenkins(server group center) and set up password authentication btwn the servers. (ssh-keygen & ssh-copy-id)(etc/ssh/sshd_config)
6. Added build steps for remote commands on docker server-> cd into custom dir(website) and build a docker img and run a conatiner from there. 
