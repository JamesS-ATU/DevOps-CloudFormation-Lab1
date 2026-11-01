# DevOps-CloudFormation-Lab1

## Overview

This project demonstrates the development of AWS CloudFormation templates through a series of enhancements focusing on:

- Infrastructure as Code (IaC)
- Parameterisation and validation
- Security best practices
- Scalable architecture design
  
Microsoft Copilot was used to generate, validate, and improve CloudFormation templates, while Visual Studio Code was used to validate YAML syntax and structure.

---

# Assignment 1 - Single Tier Web Application

## Overview

The initial solution provisions:

- EC2 Instance
- S3 Bucket
- IAM Role & Instance Profile
- Security Group

The website content is stored in S3 and served from a Linux EC2 instance.

### Original Copilot Prompt

> Create a CloudFormation script to create a website for a public facing webservice to host the website, use an S3 bucket to store the content of the web pages.

---

## Branch: InitialBranch

### Requirment

Create a working solution before introducing complexity.

### Implementation

- Single EC2 instance
- S3-hosted website content
- One configurable parameter (`ImageId`)

### Description

Starting with a simple deployment provides a stable base that can be enhanced.

---

## Branch: AddResourceTags

### Requirement

Apply consistent tags on all supported resources.

### Implementation

Common tags were added to every resource supporting AWS tagging.

### Description

Resource tagging improves:

- Cost tracking
- Resource management
- Governance and auditing

---

## Branch: Add-Parameters-For-Global-Use

### Requirement

Replace hard-coded values with reusable parameters.

### Implementation

Added parameters for:

- Student Name
- Student ID
- Environment
- Resource tags

The Student Name and Student ID are also displayed on the generated web page.

### Description

Parameterisation increases:

- Reusability
- Flexibility
- Maintainability

---

## Branch: AddConstraintsToParameters

### Requirement

Enforce validation at deployment time.

### Constraints Added

| Parameter | Constraint |
|------------|------------|
| StudentID | Must start with **L** and contain **8 digits** |
| Environment | Development, QA, UAT, Production |
| CidrBlock | Valid IPv4 CIDR block |

### Description

Input validation prevents deployment errors and promotes standardisation.

---

## Branch: AddConditionForHTTPS

### Requirement

Allow users to select HTTP or HTTPS ports.

### Implementation

- Port 80 (HTTP)
- Port 443 (HTTPS)

### Description

HTTPS is the industry standard for secure web applications.

> Note: SSL/TLS certificates are not implemented in this assignment. Port 443 is included to demonstrate consideration for secure design principles.

---

## Branch: FixIssues

### Requirement

Validate and refine the template before expanding functionality.

### Copilot Validation Prompt

> Validate this CloudFormation script. Ignore any HTML issues.

### Outcome

Resolved issues related to:

- CloudFormation best practices
- Resource configuration
- Deployment reliability

---

# Assignment 2 - Three Tier Architecture

## Branch: Create3TierArchitecture

### Requirement

Move from a single-tier deployment to a layered enterprise architecture.

### Architecture

```text
Internet
    |
 Web Tier
    |
Application Tier
    |
Database Tier
```

### Components

- Web Tier
- Application Tier
- Database Tier

### Security

Dedicated security groups were created for each tier:

- Web Security Group
- Application Security Group
- Database Security Group

Access is restricted so that each tier can communicate only with the tier directly below it.

### Description

This approach:

- Follows the Principle of Least Privilege
- Reduces the attack surface
- Improves security
- Reflects industry-standard architecture patterns

---

# Use of AI

Microsoft Copilot was used to:

- Generate initial CloudFormation templates
- Validate templates
- Identify potential issues
- Suggest architectural improvements

as much as possible, AI generated content was reviewed, tested, and refined before inclusion in the final solution.

---

# Key Outcomes

Over the course of this project, the solution evolved from a basic website deployment into a parameterised, validated, and security-focused three-tier architecture.

