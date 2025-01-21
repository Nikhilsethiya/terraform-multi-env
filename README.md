CI/CD Pipeline for Terraform Deployment
This repository contains a CI/CD pipeline configuration for automating the deployment of infrastructure using Terraform in Azure DevOps.

Pipeline Overview
The pipeline is structured into three main stages:

Validation Stage:
Performs terraform init to initialize the backend and provider.
Runs terraform validate to ensure the configuration files are syntactically correct.
Executes terraform fmt to format the Terraform configuration files.

Planning Stage:
Re-initializes the backend using terraform init.
Runs terraform plan to create an execution plan and preview the changes Terraform will apply.
Deployment Stage:

Applies the Terraform plan using terraform apply with the --auto-approve flag.

Parameters
The pipeline supports three environments: dev, staging, and prod. The environment can be specified as a parameter when triggering the pipeline. The corresponding backend configurations and variable files (<environment>.tfvars) are used for each environment.