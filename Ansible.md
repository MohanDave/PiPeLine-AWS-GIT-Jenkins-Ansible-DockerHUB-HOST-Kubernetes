.We first Configure the Ansible server on an AMAZON LINUX 2 (AMI) Machine form the AWS and configured it using putty

amazon-linux-extras install ansible2

.Docker package was aso installed on the ansible server

yum install docker

systemctl enable docker

systemctl start docker


.While adding the ansible server in the PIPELINE in the building actions and post building action following commands were given in the commands for execution column

cd /opt

docker image build -t $JOB_NAME:v1.$BUILD_ID

docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID

docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:latest

docker image push mohan1809/$JOB_NAME:v1.$BUILD_ID

docker image push mohan1809/$JOB_NAME:latest

docker image rmi $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:latest



.After that we designed our playbook on the ansible server named ansible.yml
 
-hosts: all


 become: true
 
 
        - name: create new deployment
        
        
         command: kubectl apply -f /opt/deployment.yml
         
         

        - name: create new service
        
        
         command: kubectl apply -f /opt/service.yml

