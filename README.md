# End to end Text-Summarizer-Project


This repository contains an **end-to-end text summarization system** built using **Google’s Pegasus model** and fine-tuned on the **SAMSum dataset**. It is designed to generate concise summaries for dialogues using **transformers-based NLP models**. The project includes a **modular pipeline** for **data processing, model training, evaluation, API deployment, and continuous integration/continuous deployment (CI/CD).**

---

## 🚀 Features

### 🔹 Data Processing & Preprocessing
- Handles dataset **loading, tokenization, and augmentation**.

### 🔹 Model Training & Evaluation
- Fine-tunes **Pegasus (`google/pegasus-cnn_dailymail`)** on the **SAMSum dataset**.
- Uses **ROUGE score** for performance evaluation.

### 🔹 Pipeline Components
- **Training pipeline**: Data ingestion, transformation, model training.
- **Evaluation pipeline**: Generates predictions, computes metrics.
- **Inference pipeline**: Deploys trained model for real-time summarization.

### 🔹 FastAPI-based REST API
- Exposes **endpoints** for real-time text summarization.
- Supports **batch processing** for large-scale summarization.

### 🔹 Docker Containerization
- Containerized **FastAPI application** for easy deployment.

### 🔹 AWS Deployment
- Deployed using **AWS EC2, S3, Lambda, or ECS**.

### 🔹 CI/CD Pipeline
- Automates **testing, model training, and deployment** using **GitHub Actions**.

### 🔹 Logging & Monitoring
- Implements **structured logging** for tracking model performance and errors.

## Workflows

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

Clone the repository

```bash
https://github.com/sadjad6/Text-Summarizer.git
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n summary python=3.8 -y
```

```bash
conda activate summary
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```


```bash
Author: Sadjad Sadeghi
ML Engineer
Email: sadjadsadeghi65@gmail.com

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
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/text-s

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

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

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app
