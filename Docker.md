yum install docker 

systemctl enable docker

systemctl start docker

docker login


.While adding the ansible server in the PIPELINE in the building actions and post building action following commands were given in the commands for execution column

cd /opt

docker image build -t $JOB_NAME:v1.$BUILD_ID

docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID

docker image tag $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:latest

docker image push mohan1809/$JOB_NAME:v1.$BUILD_ID

docker image push mohan1809/$JOB_NAME:latest

docker image rmi $JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:v1.$BUILD_ID mohan1809/$JOB_NAME:latest

