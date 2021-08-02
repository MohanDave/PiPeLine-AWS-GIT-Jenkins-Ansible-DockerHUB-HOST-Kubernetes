For this first installed java using the command :-


   yum install java
   
   After installing Java we used the following commands for installing Jenkins:-
   
   

 wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
 
 

 rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
 

  yum install jenkins.
  
  .Followed by starting and enabling the service:-
  
  
  . systemctl start jenkins
  
  
  . systemctl enable jenkins

The connection between the jenkins and ansible server was made passwordless by generating the key on jenkins sharing it on ansible server and enabling root login and userauthentication in the sshd_config file on the ansible server

ssh-keygen


The jenkins server sends few additional commands along with the Docker image file for its building arrangements in the ansible server itself . Commands required from the jenkins server for the operations in the ansible server are:


docker image build -t myimage:v1


docker image tag myimage:v1 (id)/myimage:v1

docker image push (id)/myimage:v1



And configured it with adding the building methods ‘send and execute files over ssh’ for jenkins and ansible server and in the post build field ‘send build artifacts over ssh’ for the ansible server.

This and the rest procedure could be seen in the  jenkins.odt file of this repository.
