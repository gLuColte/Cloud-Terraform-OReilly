![Main Banner](./markdown-images/main-banner.png)

# Cloud-Terraform-OReilly

Welcome to the Terraform Self-Learning Repository! This repository is designed to accompany your journey through the book "Terraform: Up & Running" and will serve as a hands-on workspace for practicing and mastering Terraform. As you progress chapter by chapter, you'll find structured exercises, code snippets, and challenges that align with the book's content, ensuring a practical understanding of the concepts.

## Why Infrastructure as Code (IaC)?
In today's rapidly evolving tech landscape, managing and provisioning infrastructure manually or through one-off scripts is neither scalable nor maintainable. Here's where Infrastructure as Code (IaC) comes into play:

1. **Consistency & Reproducibility**: With IaC, you can consistently reproduce your infrastructure across different stages (development, staging, production) without discrepancies.
2. **Version Control**: Just like software code, infrastructure code can be versioned, allowing teams to track changes, revert to previous states, and ensure everyone is aligned with a common infrastructure blueprint.
3. **Scalability & Speed**: IaC tools like Terraform allow for rapid provisioning and scaling of infrastructure, be it setting up a single server or deploying a global multi-region application.
4. **Reduced Human Errors**: By defining infrastructure as code, the room for manual error is significantly reduced. Infrastructure changes become reviewable, collaborative, and can be tested and validated.

### Infrastructure as Code vs. Server Templating
While server templating tools like Packer or golden images provide pre-configured server images, they don't capture the full infrastructure picture. Templates might get outdated, and maintaining them can become a challenge. IaC, on the other hand:

Defines the entire infrastructure holistically, from networks to databases.
Ensures idempotency, where re-applying configurations won't cause unintended side-effects.
Offers a more granular control and a clearer "infrastructure history" through version control.

### Other Forms of IaC
There are several IaC tools out there, each with its strengths. Tools like Ansible, Chef, or Puppet focus more on configuration management, ensuring servers are in a desired state. Cloud-specific tools like AWS CloudFormation or Azure Resource Manager templates are tightly integrated with their respective clouds but might lack flexibility or portability. Terraform stands out by offering a cloud-agnostic approach, allowing for multi-cloud strategies and ensuring you're not locked into a specific provider.

## Setup

The main setup is through:
- [LocalStack](https://github.com/localstack/localstack)
- [Use the Terraform Infrastructure as Code framework with LocalStack](https://docs.localstack.cloud/user-guide/integrations/terraform/)

Please ensure to have the necessary libraries and packages installed.

### Docker

Following [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/) to install Docker Engine.

Please ensure to enable Non-Root User Access for Docker - [How to Fix Docker Permission Denied?](https://phoenixnap.com/kb/docker-permission-denied):
```termnial
sudo groupadd -f docker
sudo usermod -aG docker $USER
newgrp docker
```

### Terraform

Please ensure to have Terraform installed - [Install Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli):

```terminal
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common
wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update
sudo apt-get install terraform
```

### Conda Environment

Create a virutal python environment and install requirements.txt

```terminal
conda env create -f environment.yml
```

**To save a conda environment**:
```terminal
conda env export | grep -v "^prefix: " > environment.yml
```

### Python Environment

If you are installing through pip

```terminal
pip install -r requirements.txt
```

**To save a python environment**:
```terminal
pip freeze > requirements.txt
```

### Initialization & Verification

**To verify tflocal is installed**:
```terminal
tflocal init
tflocal -version
```
Output the folowing:
```terminal
Terraform v1.6.2
on linux_amd64
+ provider registry.terraform.io/hashicorp/aws v5.23.1
```

**To verify localstack is installed**:

```terminal
localstack start -d
localstack status services
```
Output the folowing:
```terminal
┏━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━┓
┃ Service                  ┃ Status      ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━┩
│ acm                      │ ✔ available │
│ apigateway               │ ✔ available │
│ cloudformation           │ ✔ available │
│ cloudwatch               │ ✔ available │
│ config                   │ ✔ available │
│ dynamodb                 │ ✔ available │
│ dynamodbstreams          │ ✔ available │
│ ec2                      │ ✔ available │
│ es                       │ ✔ available │
│ events                   │ ✔ available │
│ firehose                 │ ✔ available │
│ iam                      │ ✔ available │
│ kinesis                  │ ✔ available │
│ kms                      │ ✔ available │
│ lambda                   │ ✔ available │
│ logs                     │ ✔ available │
│ opensearch               │ ✔ available │
│ ram                      │ ✔ available │
│ redshift                 │ ✔ available │
│ resource-groups          │ ✔ available │
│ resourcegroupstaggingapi │ ✔ available │
│ route53                  │ ✔ available │
│ route53resolver          │ ✔ available │
│ s3                       │ ✔ available │
│ s3control                │ ✔ available │
│ scheduler                │ ✔ available │
│ secretsmanager           │ ✔ available │
│ ses                      │ ✔ available │
│ sns                      │ ✔ available │
│ sqs                      │ ✔ available │
│ ssm                      │ ✔ available │
│ stepfunctions            │ ✔ available │
│ sts                      │ ✔ available │
│ support                  │ ✔ available │
│ swf                      │ ✔ available │
│ transcribe               │ ✔ available │
└──────────────────────────┴─────────────┘
```

### How to Use This Repository:

Place Holder