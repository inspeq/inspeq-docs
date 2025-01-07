# Inspeq On-Premise  Deployment Guide

This guide provides detailed instructions for deploying Inspeq AI platform in your AWS environment using our custom AMI. This deployment method ensures data privacy, security, and compliance with your organization's requirements.

## Prerequisites

### AWS Requirements
- Active AWS Account
- IAM user with EC2 permissions
- VPC with appropriate networking configuration
- Basic knowledge of AWS EC2 service

<!-- ### Technical Requirements
- Understanding of network security concepts
- Familiarity with Docker and container management
- Access to AWS EC2 console -->

## Deployment Process

### 1. Access Request Process

#### Required Information
Before requesting access to the Inspeq AMI, please prepare:
- AWS Account ID
- Preferred AWS Region(s)
- Expected instance type requirements
- Network requirements overview
- Technical team contact information

#### Requesting Access
1. Email partners@inspeq.ai with subject "AMI Access Request"
2. Include:
   - AWS Account ID
   - Preferred region
   - Brief description of deployment needs
3. Our team will verify your request and provide:
   - AMI ID
   - Region-specific instructions
   - Support contact information

### 2. AWS Security Configuration

#### Security Group Setup

Create a new security group with the following configurations:

##### Basic Details
| Field | Value | Description |
|-------|--------|-------------|
| Name | inspeq-service-sg | Security group name |
| Description | Security group for Inspeq service | For documentation |
| VPC | Your VPC | Example: vpc-0abfe6ff2aafa6ce0 |

##### Inbound Rules
| Type | Protocol | Port Range | Source | Description |
|------|----------|------------|---------|-------------|
| SSH | TCP | 22 | Your IP range | SSH access |
| HTTP | TCP | 80 | 0.0.0.0/0 | Web service access |
| HTTPS | TCP | 443 | 0.0.0.0/0 | Secure web service |
| Custom TCP | TCP | 9000 | 0.0.0.0/0 | Backend API access |

> **Security Note**: Consider restricting port 9000 access based on your security requirements. For enhanced security, use HTTPS (443), we can help you with that.

##### Outbound Rules
| Type | Protocol | Port Range | Destination | Description |
|------|----------|------------|-------------|-------------|
| All traffic | All | All | 0.0.0.0/0 | Allow all outbound |


##### Create Security Group

![Security Group Reference screenshot](/images/security-group-reference-1.png)

##### Sample Security Group

![Security Group Reference screenshot](/images/security-group-reference-2.png)


### 3. Instance Deployment

#### Instance Configuration
1. Navigate to EC2 in AWS Console
2. Navigate to AMIs section
3. Choose "My AMIs" > "Shared AMI"
4. Select the provided Inspeq AMI ID
5. Click on the AMI ID
6. Click on "Launch Instance"   


##### Select AMI

![Select ami ](/images/ami-selection.png)


#### Recommended Specifications

1. Give the instance a name
2. Select inspeq recommended instance type
3. Create a key pair or use an existing key pair
4. Select the security group created in the previous step
5. Configure storage : minimum 150GB
6. Click on "Launch Instance"   




##### Select instance type

![Select instance type ](/images/instance-type.png)


##### Key pair creation

![Key pair creation ](/images/key-pair.png)

##### Security group selection

![Security group selection ](/images/sg-selection.png)

##### Storage configuration

![Storage configuration ](/images/storage-config.png)

Once you click on "Launch Instance" you will be redirected to the instance details page. And instance will be created in some time.

##### Instance details

![Instance details ](/images/instance-details.png)


##### Get instance's public IP/URL

![Instance details ](/images/instance-url.png)



### 4. Post-Deployment Verification

#### Accessing the Frontend services

1. Copy the instance URL and paste it in your browser, You will be directed to the Signup/login page
2. Signup with the credentials
3. Login with the same credentials provided 
4. You will be redirected to the dashboard


##### Login page

![Instance details ](/images/landing-page.png)


##### Welcome page

![Instance details ](/images/welcome-page.png)


##### Create project

![Instance details ](/images/create-project.png)

##### Copy project keys

![Copy project keys ](/images/copy-keys.png)


##### Check created project

![Check created project ](/images/project-created.png)



#### Integrating with the Inspeq SDK

1. Follow the quickstart guide to integrate with the Inspeq SDK [Quickstart](quickstart.md)
2. Just set INSPEQ_API_URL to the instance URL:9000
3. Pass the same to inspeq_eval call inspeq_api_url

```python

from inspeq.client import InspeqEval

# Initialize the client with all required parameters
INSPEQ_API_KEY = "your_inspeq_sdk_key"
INSPEQ_PROJECT_ID = "your_project_id"
INSPEQ_API_URL = "your_instance_url:9000"  # Updated for on-prem setup

# Create InspeqEval instance with the API URL parameter
inspeq_eval = InspeqEval(
    inspeq_api_key=INSPEQ_API_KEY,
    inspeq_project_id=INSPEQ_PROJECT_ID,
    inspeq_api_url=INSPEQ_API_URL  # Added API URL parameter
)

# Prepare input data
input_data = [{
    "prompt": "What is the capital of France?",
    "response": "Paris is the capital of France.",
    "context": "The user is asking about European capitals."
}]

# Define metrics to evaluate
metrics_list = ["RESPONSE_TONE", "FACTUAL_CONSISTENCY", "ANSWER_RELEVANCE"]

try:
    # Evaluate the LLM task
    results = inspeq_eval.evaluate_llm_task(
        metrics_list=metrics_list,
        input_data=input_data,
        task_name="capital_question"
    )
    print(results)
except Exception as e:
    print(f"An error occurred: {str(e)}")
```

Now you can use the setup to evaluate your LLM tasks similar to the quickstart guide for our managed service.


## Support

### Contact Information
- Technical Support: support@inspeq.ai
- Sales Inquiries: partners@inspeq.ai
- Emergency Support: [Provided in welcome email]
