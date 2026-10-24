# DevOps-CloudFormation-Lab1
24/10/2026 - This is the Initial setup of the AWS Cloud Formation consisting of an 
              EC2 instance
              S3 Bucket
              IAM Role, profile and Security Group

              The template creates a Windows Server 2025 EC2 instance with permissions to access an S3 bucket. During deployment, a simple HTML page is generated and uploaded to the S3 bucket               before being served by the web server. There is only 1 parameter which is the ImageID and defaults to the Latest Windows 2025 Server.
