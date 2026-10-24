# DevOps-CloudFormation-Lab1
24/10/2026 - This is the Initial setup of the AWS Cloud Formation consisting of an 
              EC2 instance
              S3 Bucket
              IAM Role, profile and Security Group
The template creates a Linux EC2 instance with permissions to access an S3 bucket. 
A simple HTML page is generated and uploaded to the S3 bucket before being served by the web server. 
There is only 1 parameter which is the ImageID and defaults to the Latest Linux Image

The initial Template was generated from CoPilot using the prompt
"Create a cloudformation script to create a Website for a public facing webservice to host the website, use an s3 bucket to store the content of the web pages"

