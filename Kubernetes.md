.For Installing Kubectl on Linux we must use the following commands:-


.curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

.Make the Kubectl Binary Executable with following command:-

chmod +x kubectl

.Following Commands :-
   
.mv ./kubectl ~/.local/bin/kubectl
                                  
we modified the above command to the command below:-
.mv ./kubectl /bin/kubectl

this was because the binary path of our Amazon Linux Machine was directly bin.

.kubectl

Now installing the KOPs we have the following commands:-

.curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64

.Make the kops binary executable 

chmod +x kops-linux-amd64

.Move the kops binary in to your PATH. 

sudo mv kops-linux-amd64 /usr/local/bin/kops

.We changed it to the following:-

sudo mv kops-linux-amd64 /bin/kops


Create an S3 bucket to store your clusters state using the following commands:-




aws s3 mb s3://clusters.dev.example.com 

                             i.e.
                             
                             
aws s3 mb s3://mohandave.mohandave.in


.After that we continued by setting the Environment Variable on the Bucket created


export KOPS_STATE_STORE=s3://mohandave.mohandave.in


.After that we generated a key for its linkage with the cluster which we were going to create using the command :-



ssh-keygen




.Followed by building/creating the cluster configuration using the following modifies command:-


kops create cluster --zones=us-east-1c useast1.dev.example.com



Finally configure your cluster with:


kops update cluster useast1.dev.example.com --yes


To delete your cluster:-





kops delete cluster useast1.dev.example.com --yes






kubernetes cluster that could be seen using the command 



kubectl get nodes
kops delete cluster useast1.dev.example.com --yes




