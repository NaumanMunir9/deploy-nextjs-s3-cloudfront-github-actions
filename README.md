# Deploy NextJS App to S3 and CloudFront with Github Actions

## Video

## Introduction

- In the fast-paced world of web development, having a reliable and scalable platform for deploying applications is essential. Among the many popular frameworks, Next.js has emerged as a top choice for building robust and performant React applications with server-side rendering capabilities. However, deploying a Next.js blog app can be a daunting task, especially when it comes to managing resources, optimizing performance, and ensuring high availability. In this article, we will explore a solution that leverages Amazon S3 and CloudFront, combined with the power of GitHub Actions, to simplify the deployment process and ensure a seamless experience for both developers and end-users.

## Problem Statement and Solution

- The deployment process for Next.js applications, particularly blog apps, might involves some challenges. Scaling the application to handle increased traffic can be cumbersome, leading to potential downtime or performance bottlenecks. Moreover, maintaining an optimal caching and content delivery strategy for assets like images, CSS, and JavaScript files can be tricky, impacting the overall performance and user experience.

The combination of Amazon S3, CloudFront, and GitHub Actions provides a robust and efficient solution for deploying Next.js blog apps. Here's how this stack addresses the aforementioned challenges:

1. Simplified Deployment Process: By using GitHub Actions, developers can automate the entire deployment workflow. This means that as soon as changes are pushed to the GitHub repository, the CI/CD pipeline will automatically build, test, and deploy the Next.js app to Amazon S3 and CloudFront, reducing the need for manual intervention.

2. Scalability and High Availability: Amazon S3 offers virtually unlimited storage capacity, and CloudFront is a globally distributed Content Delivery Network (CDN). This combination ensures that the Next.js blog app can scale effortlessly to handle any amount of traffic while providing low-latency access to users across the globe.

3. Efficient Caching and Content Delivery: CloudFront acts as a CDN and caches assets like images, CSS, and JavaScript files at edge locations. This optimizes content delivery, reduces server load, and minimizes the load time for end-users, resulting in a faster and more responsive experience.

4. Cost-Effective Solution: By utilizing serverless resources like S3 and CloudFront, the cost of hosting and delivering the Next.js blog app is significantly reduced. You only pay for the resources you consume, making it an economical choice for small to large-scale projects.

## Architecture Diagram

![Deploy NextJS App to S3 and CloudFront with Github Actions](/architecture-diagram/DeployNextJSApptoS3andCloudFrontwithGithubActions.png)

## Project Walkthrough

### Create NextJS App

### Push Source Code to GitHub

### Create S3 Bucket

#### Setting permissions for website access

[Setting permissions for website access](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteAccessPermissionsReqd.html)

- When you configure a bucket as a static website, if you want your website to be public, you can grant public read access. To make your bucket publicly readable, you must disable block public access settings for the bucket and write a bucket policy that grants public read access. If your bucket contains objects that are not owned by the bucket owner, you might also need to add an object access control list (ACL) that grants everyone read access.

### Create CloudFront Distribution

### Integrate AWS with Github for Github Actions Workflow

#### IAM roles to connect GitHub Actions to actions in AWS

[Use IAM roles to connect GitHub Actions to actions in AWS](https://aws.amazon.com/blogs/security/use-iam-roles-to-connect-github-actions-to-actions-in-aws/)

- the steps needed to configure a specific GitHub repo to assume an individual role in an AWS account to preform changes.
- Learn how to create an OIDC-trusted connection that is scoped to an individual GitHub repository, and how to map the repository to an IAM role in your account. You will create the OIDC connection, IAM role, and trust relationship.

#### Configuring OpenID Connect in Amazon Web Services

[Configuring OpenID Connect in Amazon Web Services](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services)

- Use OpenID Connect within your workflows to authenticate with Amazon Web Services.
- OpenID Connect (OIDC) allows your GitHub Actions workflows to access resources in Amazon Web Services (AWS), without needing to store the AWS credentials as long-lived GitHub secrets.
