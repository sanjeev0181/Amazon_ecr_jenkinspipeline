# Amazon_ecr_jenkinspipeline

https://medium.com/@vijulpatel865/building-docker-image-using-jenkins-pipeline-push-it-to-aws-ecr-aa02cc7a295e


# Install AWS CLI , Docker on jenkins server
apt install awscli -y

curl -fsSL https://get.docker.com -o install-docker.sh

sh install-docker.sh

Install the most recent Docker Engine package

sudo amazon-linux-extras install docker

Now start docker services

sudo service docker start

Add the ec2-user to the docker group, so you can execute Docker commands without using sudo

sudo usermod -a -G docker ec2-user

After that restart Jenkins and Docker by following commands

sudo service jenkins restart

sudo service docker restart



# Create IAM role and attach policy 

Now create an IAM role with AmazonEC2ContainerRegistryFullAccess policy and attach it with ec2 instance

