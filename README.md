# End to end Text-Summarizer

# Introduction
It is an end-to-end NLP project based on transformers using the Hugging Face API, where I fine-tuned the "google pegasus-cnn_dailymail" model on the SAMSum dataset to generate concise summaries of dialogues. The project included creating a comprehensive training and prediction pipeline encompassing data ingestion, validation, transformation, and model training, all integrated into a seamless workflow for text summarization. To showcase the model's functionality, I developed a user-friendly application using FastAPI, allowing users to input dialogues and receive summarized outputs. Utilizing GitHub Actions for CI/CD, I deployed the project on AWS Cloud, ensuring continuous integration and delivery.

## Workflow for Modular Coding

1. Update config.yaml
2. Update params.yaml
3. Update entity
4. Update the configuration manager in src config
5. update the conponents
6. update the pipeline
7. update the main.py
8. update the app.py


# How to run?
### STEPS:

First clone the repository

```bash
https://github.com/Hustler-15/Text_Summarizer
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n textS python=3.8 -y
```

```bash
conda activate textS
```


### STEP 02- Install the requirements.txt
```bash
pip install -r requirements.txt
```


```bash
# Run the app.py
python app.py
```

Now,
```bash
open up you local host and port
```


```bash
Author: Ankit Pal
Email: ap644531@gmail.com

```



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 730335214290.dkr.ecr.eu-north-1.amazonaws.com/text-s

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal(Update Package Manager)

	sudo apt-get update -y

	sudo apt-get upgrade
	
	# Install the docker on EC2 Instance

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>> 730335214290.dkr.ecr.eu-north-1.amazonaws.com

    ECR_REPOSITORY_NAME = text-s
