# CloudGuard – AWS IAM Policy Checker

## About the Project

CloudGuard is a small project I built to check AWS IAM policies and understand what permissions they contain. While working with AWS, I wanted to explore how policy validation works and how we can identify permissions that might be too broad.

The tool allows users to paste an IAM policy in JSON format and analyze it through a simple web interface. It uses AWS IAM Access Analyzer to get validation findings and also runs a few custom checks for risky permission patterns.

## Why I Built CloudGuard

IAM policies control what actions users and services can perform in AWS. If a policy grants more permissions than required, it can create security risks.

I built CloudGuard to make it easier to test IAM policies and see the findings in one place. It is a learning project through which I explored AWS services, API integration, and basic cloud security concepts.

## Features

- Analyze IAM policies written in JSON.
- Get policy validation findings from AWS IAM Access Analyzer.
- Identify selected broad-permission patterns using custom rules.
- View AWS findings separately from custom findings.
- Display an error message when the input contains invalid JSON.

## Technologies Used

- HTML, CSS and JavaScript for the frontend
- Python for the AWS Lambda backend
- Amazon API Gateway to connect the frontend with the backend
- AWS IAM Access Analyzer for policy validation
- GitHub Pages to host the website

## How It Works

1. The user opens the CloudGuard website and enters an IAM policy.
2. The frontend sends the policy to an API Gateway endpoint.
3. API Gateway forwards the request to an AWS Lambda function.
4. Lambda calls AWS IAM Access Analyzer to validate the policy.
5. Custom checks examine selected permission patterns.
6. The results are returned to the frontend and displayed to the user.

## Testing

I tested the application with different inputs, including a normal S3 read policy, a policy containing wildcard permissions, and invalid JSON.

These tests helped me check whether the application could send requests to AWS, display validation findings, and handle incorrect input. I also worked on resolving a CORS issue when connecting the deployed website to the AWS backend.

## Live Demo

Try CloudGuard here:

https://abhinav09-ai.github.io/CloudGuard/

## GitHub Repository

Source code:

https://github.com/Abhinav09-ai/CloudGuard

## Current Limitations

CloudGuard currently uses AWS IAM Access Analyzer and custom rule-based checks. It does not guarantee that a policy is completely secure, because the actual risk also depends on the surrounding AWS environment and how permissions are used.

This is an initial working prototype, and there is room to improve its analysis, user experience, and security checks.

## What I Learned

While building this project, I got practical experience connecting a frontend to AWS services using API Gateway and Lambda. I also learned about IAM policy validation, CORS configuration, and deploying a website using GitHub Pages.

The project gave me an opportunity to apply cloud computing and security concepts in a working application.
