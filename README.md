
# CONTINUOS INTEGRATION WITH WINDOWS JENKINS FOR ANGULAR

* #### First need to install NodeJs(14.15.0), Angular CLI(12.2.17) and pkg(5.8.1) on your windows.

* #### Now open your command prompt and enter below commands to know the installation path of the above three pakages:
```bash
  where Node
  where ng
  where pkg
```
* #### Now get the installation paths and paste it into environment variables in your windows system.







# CONTINUOS INTEGRATION WITH WINDOWS JENKINS FOR ANGULAR

* #### First need to install NodeJs(14.15.0), Angular CLI(12.2.17) and pkg(5.8.1) on your windows.

* #### Now open your command prompt and enter below commands to know the installation path of the above three pakages:
```bash
  where Node
  where ng
  where pkg
```
* #### Now get the installation paths and paste it into environment variables in your windows system.

![Screenshot (159)](https://github.com/Devopshub123/CI-CD-WITH-WINDOWS-JENKINS-FOR-ANGULAR/assets/128797715/906d2527-c778-4b2c-8d5c-82eb77984683)

* #### Now intsall the below plugins in your JENKINS
```bash
1. NodeJs
2. Publish Over ssh
3. Build Pipeline plugin
```
* #### Now create Five jobs as named as:
```bash
 Clonning
 Build-Excecution
 Archivng
 Copying to Docker Server
 Deploying to containers
```
* #### After installing the build pipeline plugin you will see an option called "My Views"

![Screenshot (162)](https://github.com/Devopshub123/CI-CD-WITH-WINDOWS-JENKINS-FOR-ANGULAR/assets/128797715/5881f62c-74f0-4e90-9961-00643bae0ea2)

* #### Next click on "+" symbol button to configure upstream and downstream jobs to make a pipeline

![Screenshot (164)](https://github.com/Devopshub123/CI-CD-WITH-WINDOWS-JENKINS-FOR-ANGULAR/assets/128797715/c51be8f7-a4ae-4134-8b30-c636b1768823)

* #### Now Give a name to the view and select an option called "Build Pipeline View" and click on create :

![Screenshot (165)](https://github.com/Devopshub123/CI-CD-WITH-WINDOWS-JENKINS-FOR-ANGULAR/assets/128797715/af065a7d-87a6-45e7-b285-d12d5ad922a2)

* #### Next in upstream and downstream config section select the intial job to run "Clonning"

![Screenshot (166)](https://github.com/Devopshub123/CI-CD-WITH-WINDOWS-JENKINS-FOR-ANGULAR/assets/128797715/03bbd712-236e-4946-88e0-12fb74f73ac0)

* #### Next select the below options:

![Screenshot (167)](https://github.com/Devopshub123/CI-CD-WITH-WINDOWS-JENKINS-FOR-ANGULAR/assets/128797715/c688c059-fa3c-4e0c-ba5a-a41b5dc79218)

* #### Next select the number build pipelines to display and click on apply and OK:

![Screenshot (168)](https://github.com/Devopshub123/CI-CD-WITH-WINDOWS-JENKINS-FOR-ANGULAR/assets/128797715/7e12fd83-59cc-4e37-8129-de5d7346fcc4)

### Add docker server in jenkins system configuration to recieve build artifacts:

* #### First install the docker on the docker server

* Next add the ubuntu user to docker group to execute commands :
```bash
 sudo usermod -aG docker ubuntu 
```
* Next set a password for your ubuntu user in docker machine :
```bash
 sudo passwd ubuntu

 Enter New password and confirm it
```
* Next we have to enable password based authentication from jenkins to docker :
```bash
 sudo vim /etc/ssh/sshd_config
```
* Now we have to change PasswordAuthentication no to yes :

![Screenshot (2)](https://user-images.githubusercontent.com/98937778/211364192-68fc69d4-8844-4b02-b908-e04f30130cbc.png)

* Next change it to yes and save the file :
* Next restart the sshd service 
```bash
 service sshd restart 
```
* Next give the full permission to your remote directory :
```bash
 sudo chmod -R 777 /home/ubuntu
```
* And also add the permission for another file :
```bash
 sudo chmod 777 /var/run/docker.sock
```

* In jenkins click on configure systems :
* and scroll down you will see publish over ssh as shown below :

![Screenshot (3)](https://user-images.githubusercontent.com/98937778/211365929-0cf73fcc-e3c1-4e50-9cc0-93af0bd48633.png)

* Then in the ssh servers section click on Add :
* Next fill the details like below and click on Advanced.. :

![Screenshot (4)](https://user-images.githubusercontent.com/98937778/211366731-7091d363-a199-4cbc-b687-8c68ee3641c4.png)

* Next click on the check box and give the password of the ubuntu user which we previuosly set :

![Screenshot (5)](https://user-images.githubusercontent.com/98937778/211367305-ec00f32f-6068-4d38-97a9-f1f94b593490.png)

* Next scroll down and click on Test Configuration then it showing as success next click on apply and save :

![Screenshot (6)](https://user-images.githubusercontent.com/98937778/211367970-94102c7a-c283-4065-9b53-4c54d73c5139.png)














