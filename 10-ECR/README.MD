# ECR[Elastic Container Registry]
* ECR is used to store and manage the Container's
* ECR is AWS service that is a container registry similar to docker hub
* The primary thing in ECR is to store the docker images

# ECR VS DockerHub
* DockerHub is free initially we can login and we can create an account with dockerhub and we can create public repository  in dockerhub

# What is Public Repository
* When we push our docker image's into public repository everyone in the world can see and download our image's
* We can create privite repository in dockerhub but only authorized people can see image's and download who have access to the repository they can view everything

# ECR
* ECR is mainly supports the privite repository when we can a repository by default is enables the privite repo
* ECR mainly focus on security 

# Key Benefits of ECR
* Security: ECR offers encryption at rest, and images are stored in private repositories by default, ensuring the security of your container images
* Scalability: As a managed service, ECR automatically scales to meet the demands of your container image storage
* Availability: ECR guarantees high availability, reducing the risk of image unavailability during critical times

# Getting Started with AWS ECR
# Creating an ECR Repository
* Go to the AWS Management Console and navigate to the Amazon ECR service
* Click on "Create repository" to create a new repository
* Enter a unique name for your repository and click "Create repository"

# Installing AWS CLI
* To interact with ECR from your local machine, you'll need to have the AWS Command Line Interface (CLI) installed. Follow the instructions in the AWS CLI User Guide to install it.

# Configuring AWS CLI
* After installing the AWS CLI, open a terminal and run the following command to configure your CLI with your AWS credentials:
* Run aws configure
* Enter your AWS Access Key ID, Secret Access Key, default region, and preferred output format when prompted.

4. Pushing Docker Images to ECR
Now that you have your ECR repository set up and the AWS CLI configured, let's push a Docker image to ECR.

Build your Docker image locally using the docker build command:
docker build -t <your-image-name> <path-to-dockerfile>
Tag the image with your ECR repository URI:
docker tag <your-image-name>:<tag> <your-aws-account-id>.dkr.ecr.<your-region>.amazonaws.com/<your-repository-name>:<tag>
Log in to your ECR registry using the AWS CLI:
aws ecr get-login-password --region <your-region> | docker login --username AWS --password-stdin <your-aws-account-id>.dkr.ecr.<your-region>.amazonaws.com
Push the Docker image to ECR:
docker push <your-aws-account-id>.dkr.ecr.<your-region>.amazonaws.com/<your-repository-name>:<tag>
5. Pulling Docker Images from ECR
To pull and use the Docker images from ECR on another system or AWS service, follow these steps:

Log in to ECR using the AWS CLI as shown in Step 3 of the previous section.
Pull the Docker image from ECR:
docker pull <your-aws-account-id>.dkr.ecr.<your-region>.amazonaws.com/<your-repository-name>:<tag>
