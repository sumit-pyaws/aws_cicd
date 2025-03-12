# Data Engineering Infrastructure with AWS & Terraform 🚀

This repository contains the infrastructure and automation scripts for managing AWS services using Terraform and CI/CD pipelines. It includes AWS Glue, Apache Airflow, Lambda, and deployment automation via GitHub Actions and AWS CodePipeline.

---
terraform/ → Contains Terraform configurations for AWS infrastructure

backend.tf → Defines remote state storage (S3 & DynamoDB)
main.tf → Core Terraform configurations
provider.tf → AWS provider setup
variables.tf → Input variables
outputs.tf → Terraform output variables
glue_jobs/ → AWS Glue ETL scripts

airflow/ → Apache Airflow DAGs for orchestration

lambdas/ → AWS Lambda functions

scripts/ → Utility scripts (Python/Bash)

ci-cd/ → CI/CD configurations

buildspec.yml → AWS CodeBuild build script
codepipeline.tf → Terraform for AWS CodePipeline setup
codebuild.tf → Terraform for AWS CodeBuild setup
github-actions/ → GitHub Actions workflows

deploy.yml → GitHub Actions CI/CD workflow
data-engineering.code-workspace → VS Code workspace file