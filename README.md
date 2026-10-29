<h1> DevOps-CloudFormation-Lab1</h1>
<h2>CloudformationAssignment_1.yaml</h2>
<h3>Branch:InitialBranch</h3>

This is the Initial setup of the AWS Cloud Formation consisting of an:

+ EC2 instance
+ S3 Bucket
+ IAM Role, profile and Security Group

The template creates a Linux EC2 instance with permissions to access an S3 bucket. 
A simple HTML page is generated and uploaded to the S3 bucket before being served by the web server. 
There is only 1 parameter which is the ImageID and defaults to the Latest Linux Image

The initial Template was generated from CoPilot using the prompt
> Create a cloudformation script to create a Website for a public facing webservice to host the website, use an s3 bucket to store the content of the web pages

<h3>Branch:AddResourceTags</h3>

Good practice dictates that each resource that supports tagging should be tagged. There doesnt seem to be a Global tagging resource or object that can be referenced by all resources globally so the same tags have been applied to all 

<h3>Branch: Add-Parameters-For-Global-Use </h3>
Replace Hardcoded Tags with Parameters which are then referenced throughout the script and name and studentID are added to the HTML

<h3>Branch: AddConstraintsToParameters </h3>

Add Constraints to Parameters
+ StudentID is constrained to starting with L and having 8 Digits
+ Environment is constrained to Development, QA, UAT and Production
+ CidrBlock Must be a valid IPv4 CIDR block

<h3>Branch: AddConditionForHTTPS</h3>
Added in a Parameter to select Port 80 or 443, This is to signify HTTP or HTTPS. Most Modern websites should default to HTTPS for Security Concerns. 
For this Demo because SSL Certificates are not defined I am just using 443 as a Placeholder 

<h2>CloudformationAssignment_2.yaml</h2>
<h3>Branch:Create3TierArchitecture</h3>
Using the YAML created in assignment 1, CloudFormationAssignment_2.yaml was created to implement a 3 tier architecture that includes:

+ Web Tier
+ Application Tier 
+ Database tier.

For this architecture each tier will only be able to access the preceding tier, i.e. Web -> Application -> Database
This is demonstrated through the Security groups:

+ Web Security Group
+ Application Security Group
+ Database Security Group

> This project used Copilot for initial Template Creation and Validation and Visual Studio Code to Validate Syntax and structure  
