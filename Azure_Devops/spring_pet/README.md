building spring pet clinic application
--------------------------------------
1. sudo apt update -y
2. sudo apt install openjdk-17-jdk -y
3. sudo apt install maven -y
4. git clone https://github.com/nkishore555/spring-petclinic.git [referhere](https://github.com/nkishore555/spring-petclinic.git) for git hub      spring pet clinic application
5. cd spring-petclinic
6. ./mvnw package
7. cd /target here you will see your created jar file

aws cli configure
-----------------
1. apt install unzip -y
2. curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" [referhere](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) refer here for aws cli install
3. unzip awscliv2.zip
4. sudo ./aws/install
5. aws --version

create Iam user and s3 bucket
--------------------------------
1. create an IAM user and get access id and secret key to configure 
2. aws cofigure
3. aws s3 ls
4. aws s3 mb s3://krrish387 [referhere](https://docs.aws.amazon.com/cli/latest/reference/s3/mb.html) refer here for creating s3 bucket
5. aws s3 cp spring-petclinic-3.0.0-SNAPSHOT.jar s3://krrish387 [referhere](https://docs.aws.amazon.com/cli/latest/reference/s3/cp.html#examples) refere here for copying files to s3 from cli
6. we have to make our s3 bucket and obtects to public otherwise we can't access our files
7. we will get url for our uploaded object
8. wget https://krrish387.s3.ap-south-1.amazonaws.com/spring-petclinic-3.0.0-SNAPSHOT.jar we have to mention exact path where ever we downloaded our jar file in the spring.service file
9. cd /etc/systemd/system/
10. vi spring.service
```
[Unit]
Description=Springpetclinic service
[Service]
User=ubuntu
WorkingDirectory=/home/ubuntu
ExecStart=/usr/bin/java -jar spring-petclinic-3.0.0-SNAPSHOT.jar
SuccessExitStatus=101
TimeoutStopSec=10
Restart=on-failure
RestartSec=5
[Install]
WantedBy=multi-user.target
```
11. sudo systemctl daemon-reload
12. sudo systemctl enable --now spring.service
13. sudo systemctl start spring.service
14. sudo systemctl status spring.service
15. ipaddress:8080
    
spring application from ansible
-------------------------------
1. install ansible and setup ansible
2. vi hosts
3. vi spring.yml [referhere](https://github.com/nkishore555/joip_docs_QT/blob/main/Azure_Devops/spring_pet/spring.yml) refere here for playbook
4. ansible-playbook -i hosts spring.yml

spring application from azure devops pipeline
---------------------------------------------
1. first we need to import the code from github to azure repos [referhere](https://github.com/nkishore555/joip_docs_QT/blob/main/Azure_Devops/spring_pet/azure_devops_spring.yml) refer here for the azure pipeline code
```pipeline code
---
pool:
  name: "kishore"

trigger:
  - main

steps:
- script: |
    ansible-playbook -i hosts spring.yml
  workingDirectory: /home/kishore
  displayName: my playbook to install spring pet clinic application
```
2. select pileline then select new pipeline slelect our repo
3. select existing yml file then click ok RUN icon your application will start run


