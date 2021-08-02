# PiPeLine-AWS-GIT-Jenkins-Ansible-DockerHUB-HOST-Kubernetes
Our project includes developement of a Continuous Integration and Continuous Delivery DevOps Pipeline for deployment of the job on the 
Kubernetes cluster. In this project we deployed a docker file on the kubernetes cluster using Jenkins , Ansible and DockerHub.
Our Pipeline operation involves deployment of the Docker Image file by the developer on GitHube repository to the jenkins server followed by its 
building on ansible server and creation of an image of this file on our DockerHub repository from where it is deployed on any of the worker nodes 
by the Master Node in the Kubernetes cluster by the Controller machine.

Kindly read the .odt files for knowing the detailed procedure with screenshots and commands and for crucial commands used kindly refer to the .md files.
----------------------------------------------------------------------------------------------------------------------------------------------------------


This was our docker image file on the GITHUB repository provided by the developer.
![image](https://user-images.githubusercontent.com/87275524/127894150-d82e7947-95b9-4091-9ddf-81b865df5476.png)
(INITIAL POINT  OF OUR PIPELINE THE DOCKER FILE BY THE DEVELOPER ON THE GITHUB REPOSITORY)

![Screenshot (373)](https://user-images.githubusercontent.com/87275524/127895718-fbb56f42-e11a-48ea-87b4-70127154ba72.png)
 (FINAL DEPLOYMENT ON KUBERNETES CLUSTER WORKER NODE IN OUR PIPELINE)

 



