# Data Engineering Infrastructure with AWS & Terraform 🚀

This repository contains the infrastructure and automation scripts for managing AWS services using Terraform and CI/CD pipelines. It includes AWS Glue, Apache Airflow, Lambda, and deployment automation via GitHub Actions and AWS CodePipeline.

---
aws_cicd/
│── terraform/                     # Infrastructure as Code (IaC) with Terraform
│   ├── modules/                    # Reusable Terraform modules
│   │   ├── glue/                    # AWS Glue module
│   │   ├── s3/                      # S3 bucket module
│   │   ├── redshift/                # Redshift cluster module
│   │   ├── airflow/                 # MWAA (Managed Workflow) module
│   │   ├── lambda/                  # AWS Lambda functions
│   │   ├── iam/                     # IAM roles and policies
│   │   ├── sns/                     # SNS notifications
│   │   ├── athena/                  # Athena setup
│   │   ├── cloudwatch/              # CloudWatch logging and monitoring
│   │   └── vpc/                     # VPC, subnets, and security groups
│   ├── envs/                        # Environment-specific configurations
│   │   ├── dev.tfvars               # Development environment
│   │   ├── qa.tfvars                # QA environment
│   │   ├── prod.tfvars              # Production environment
│   ├── main.tf                      # Main Terraform configuration
│   ├── variables.tf                 # Variable definitions
│   ├── outputs.tf                   # Outputs for Terraform resources
│   ├── providers.tf                 # Provider configurations
│   ├── backend.tf                    # Remote state backend (S3 + DynamoDB)
│   ├── terraform.tfvars             # Default variable values
│   ├── versions.tf                  # Terraform version constraints
│   ├── README.md                     # Documentation for Terraform setup
│
│── dags/                            # Apache Airflow DAGs for orchestration
│   ├── README.md                     # Airflow DAG documentation
│
│── glue_jobs/                        # AWS Glue scripts
│   ├── ingestion_script.py            # Glue job for raw data ingestion
│   ├── transformation_script.py       # Glue job for transformations
│   ├── validation_script.py           # Glue job for data validation
│   ├── redshift_load_script.py        # Glue job for Redshift load
│   ├── README.md                      # Glue job documentation
│
│── lambdas/                          # AWS Lambda functions
│   ├── notify_failure/                # Lambda function for notifications
│   │   ├── lambda_function.py
│   │   ├── requirements.txt
│   ├── trigger_glue/                  # Lambda to trigger Glue jobs
│   │   ├── lambda_function.py
│   │   ├── requirements.txt
│   ├── README.md                      # Lambda function documentation
│
│── sql/                              # SQL scripts for Redshift and Athena
│   ├── create_tables.sql              # Table creation scripts
│   ├── transformations.sql            # Transformation queries
│   ├── validation_queries.sql         # Validation SQL scripts
│   ├── athena_queries.sql             # Athena queries
│   ├── README.md                      # SQL script documentation
│
│── config/                           # Configuration files
│   ├── connections.json               # Database connections
│   ├── s3_buckets.json                # S3 bucket configurations
│   ├── glue_configs.json              # Glue job configurations
│   ├── airflow_connections.json       # Airflow connections
│   ├── README.md                      # Configuration documentation
│
│── scripts/                          # Utility scripts (Bash, Python)
│   ├── data_validation.py             # Data validation utility
│   ├── s3_cleanup.sh                  # Script to clean up S3 files
│   ├── glue_job_trigger.py            # Script to trigger Glue jobs manually
│   ├── README.md                      # Script documentation
│
│── tests/                            # Unit and integration tests
│   ├── test_glue_jobs.py              # Glue job test cases
│   ├── test_airflow_dags.py           # Airflow DAG test cases
│   ├── test_lambda_functions.py       # Lambda function test cases
│   ├── test_sql_queries.py            # SQL validation tests
│   ├── README.md                      # Test documentation
│
│── docs/                             # Documentation for the project
│   ├── architecture_diagram.png       # System architecture
│   ├── data_flow.md                   # Data flow documentation
│   ├── terraform_setup.md             # Terraform setup guide
│   ├── deployment_guide.md            # Deployment steps
│   ├── troubleshooting.md              # Common issues and solutions
│
│── .github/                           # GitHub Actions for CI/CD
│   ├── workflows/
│   │   ├── terraform-ci.yml            # CI for Terraform
│   │   ├── glue-ci.yml                 # CI for Glue Jobs
│   │   ├── airflow-ci.yml              # CI for Airflow DAGs
│   │   ├── lambda-ci.yml               # CI for Lambda functions
│
│── .gitignore                         # Ignore unnecessary files
│── README.md                          # Project overview and setup instructions
│── Makefile                           # Commands for build, test, deploy
│── requirements.txt                    # Python dependencies
│── Dockerfile                          # Containerization setup (if needed)
