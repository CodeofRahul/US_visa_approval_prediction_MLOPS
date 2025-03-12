[![MLOps](https://img.shields.io/badge/MLOps-Enabled-green)]()
[![Pipeline](https://img.shields.io/badge/Pipeline-Automated-blue)]()
[![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-blue?logo=github)](https://github.com/features/actions)
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Enabled-orange)]()
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/release/python-380/)


# US_visa_approval_prediction_MLOPS

This project implements an end-to-end **Machine Learning Operations (MLOps)** pipeline to predict the approval status of US visa applications. By leveraging a comprehensive dataset containing various applicant and job-related features, I aim to build a robust model capable of accurately predicting whether a visa application will be certified or denied. This project showcases a full MLOps workflow, including data ingestion, validation, transformation, model training, evaluation, CICD and deployment, all within a structured and scalable architecture.


## Problem Statement:
**US visa approval status** <br>
Given certain set of feature such as (continent, education, job-experience, training, employment, current age etc.)
I have to predict weather the application for the visa will be approved or not.

**Data Structure and Features:**

- **continent:** The continent of the employee.
- **education_of_employee:** The highest level of education attained by the employee.
- **has_job_experience:** A binary variable indicating whether the employee has job experience (Y/N).   
- **requires_job_training:** A binary variable indicating whether the job requires training (Y/N).
- **no_of_employees:** The number of employees in the company.
- **yr_of_estab:** The year the company was established.
- **region_of_employment:** The region of employment in the US.
- **prevailing_wage:** The prevailing wage offered for the position.
- **unit_of_wage:** The unit of the prevailing wage (Hour/Year).
- **full_time_position:** A binary variable indicating whether the position is full-time (Y/N).   
- **case_status:** The target variable, indicating whether the visa application was certified or denied.

**Solution Scope:** <br>
This can be used on real life by Us visa applicants so that they can improve their Resume and criteria for the approval process.

**Solution Approach:** <br>
1.	Machine learning : ML Classification Algorithms
2.	Deep Learning: Custom ANN with sigmoid activation Function

**Solution Proposed:** <br>
I will be using ML
1.	Load the data from DB
2.	Perform EDA and feature engineering to select the desirable features.
3.	Fit the ML classification Algorithm and find out which one performs better.
4.	Select top few and tune hyperparameters.
5.	 Select the best model based on desired metrics.

## Key Features

* **Automated MLOps Pipeline:** A complete pipeline for data processing, model training, and deployment, ensuring reproducibility and efficiency.
* **Data Validation and Transformation:** Rigorous data validation to maintain data quality and effective transformation for optimal model performance.
* **Model Training and Evaluation:** Utilization of advanced machine learning techniques to build and evaluate predictive models.
* **Continuous Integration/Continuous Deployment (CI/CD):** Automated deployment using CI/CD pipelines for seamless updates.
* **Scalable Architecture:** Modular design for easy expansion and maintenance.
* **MongoDB Integration:** Utilizes MongoDB for data storage and retrieval, demonstrating database connectivity.
* **Comprehensive Logging and Exception Handling:** Robust logging and exception handling for improved monitoring and debugging.






```Powershell
to create file using CMD/Powershell : type <filename> (type template.py)
```


- To create environment = `conda create -p visa python=3.8 -y`
- To check available envs = `conda env list`
- To check available envs = `conda info --envs`
- To activate environment = `conda activate visa`
- To install requirements.txt = `pip install -r requirements.txt`
- To check install packages = `pip list`
- To check detailed about package = `pip show package_name`
- To install package = `pip install package_name`
- To uninstall package = `pip uninstall package_name`


```python
>>> from pathlib import Path
>>> path = "test/test.py"
>>> path = "test/test.py"
>>> Path(path)
WindowsPath('test/test.py')
```

## Git commands 

- To add all file = `git add .`
- To add any particular file = `git add <file_name>`
- To commit = `git commit -m "commit message"`
- To push the code = `git push origin main`


- MongoDB : https://account.mongodb.com/account/login


## Workflow:

1. constants
2. entity
3. components
4. pipelines
5. Main file

### Export the environment variable
```bash

export MONGODB_URL="mongodb+srv://<username>:<password>...."

export AWS_ACCESS_KEY_ID = <AWS_ACCESS_KEY_ID>

export AWS_SECRET_ACCESS_KEY = <AWS_SECRET_ACCESS_KEY>

```



### How Amazon S3 works

Amazon S3 stores data as objects within buckets. An object is a file and any metadata that describes the file. A bucket is a container for objects. To store your data in Amazon S3, you first create a bucket and specify a bucket name and AWS Region. Then, you upload your data to that bucket as objects in Amazon S3. Each object has a key (or key name), which is the unique identifier for the object within the bucket.

S3 provides features that you can configure to support your specific use case. For example, you can use S3 Versioning to keep multiple versions of an object in the same bucket, which allows you to restore objects that are accidentally deleted or overwritten. Buckets and the objects in them are private and can only be accessed with explicitly granted access permissions. You can use bucket policies, AWS Identity and Access Management (IAM) policies, S3 Access Points, and access control lists (ACLs) to manage access.

## AWS-CICD-Deployment-with-Github-action 

### 1. Login to AWS console.

### 2. Create IAM user for deployment 

```python

# with specific access

1. EC2 access : It is virtual machine

2. ECR: Elastic Container registry to save your docker image in aws


# Description: About the deployment

1. Build docker image of the source code

2. Push your docker image to ECR

3. Launch Your EC2

4. Pull Your image from ECR in EC2

5. Launch your docker image in EC2

# Policy:

1. AmazonEC2ContainerRegistryFullAccess

2. AmazonEC2FullAccess

```

### 3. Create ECR repo to store/save docker image

```
Save the URI: 315865595366.dkr.ecr.us-east-1.amazonaws.com/visarepo
```

### 4. Create EC2 machine (Ubuntu)

### 5. Open EC2 and Install docker in EC2 Machine:

```
#optinal

sudo apt-get update -y

sudo apt-get upgrade

#required

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```

### 6. Configure EC2 as self-hosted runner:

```
setting>actions>runner>new self hosted runner> choose os> then run command one by one
```

### 7. Setup github secrets:

- AWS_ACCESS_KEY_ID
- AWS_SECRET_ACCESS_KEY
- AWS_DEFAULT_REGION
- ECR_REPO
