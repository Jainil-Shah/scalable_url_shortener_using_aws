# Scalable URL Shortener using AWS Services

## Overview

This project demonstrates a cloud-native URL Shortener built on AWS, utilizing various AWS services for scalability, security, and performance. The application allows users to generate short URLs, track click analytics, and ensure high availability using AWS best practices.

## Features

- Convert long URLs into short, easily shareable links.
- Redirect short URLs to their original destinations.
- Track click analytics such as the number of visits and popular links.

## AWS Services Used

- **AWS S3** – Hosts static frontend files.
- **AWS API Gateway** – Exposes API endpoints.
- **AWS Lambda (Python/Node.js)** – Handles URL processing.
- **AWS DynamoDB** – Stores URL mappings and analytics.
- **AWS CloudFront** – Ensures global content delivery.
- **AWS IAM** – Manages security and access control.
- **AWS CloudWatch** – Provides logging and monitoring.

## Architecture

1. **Frontend (React/HTML+JS)** hosted on **S3**, served via **CloudFront**.
2. **API Gateway** exposes endpoints to interact with backend logic.
3. **Lambda Functions** handle business logic (shortening URLs, redirection, and analytics).
4. **DynamoDB** stores short URLs and analytics data.
5. **CloudFront** optimizes global delivery of the frontend.
6. **IAM Roles** secure access to AWS services.

## Implementation Plan

### Frontend

- Develop a simple UI with an input box for URL shortening.
- Display generated short links and analytics.
- Deploy frontend files to an **S3 Bucket** with public access.

### Backend

- Create an **API Gateway** with the following endpoints:
  - `POST /shorten` → Accepts a long URL, generates a short ID, and stores it in **DynamoDB**.
  - `GET /{shortID}` → Redirects users to the original URL.
  - `GET /analytics` → Fetches click data.
- Develop **Lambda functions (Python/Node.js)** to handle these requests.
- Integrate **DynamoDB** for storage and tracking.

### Deployment & Security

- Use **CloudFront** to distribute frontend globally.
- Configure **IAM Roles & Policies** for secure access.
- Enable **CloudWatch Logs & Metrics** for monitoring API requests.

## Deployment & Testing

### Deploy Frontend

1. Upload frontend files to an **S3 bucket**.
2. Enable public access and static website hosting.
3. Configure **CloudFront** for global delivery.

### Deploy Backend

1. Deploy **Lambda functions** and connect them to API Gateway.
2. Create and configure **DynamoDB tables** for URL storage.
3. Configure API Gateway routes for endpoints.
4. Enable **IAM permissions** for secure access.

### Testing

1. Shorten a URL using `POST /shorten`.
2. Visit the generated short URL to check redirection.
3. Fetch analytics using `GET /analytics`.
4. Monitor API requests and errors in **CloudWatch**.

## Repository Setup & GitHub Deployment

### Initialize a Git repository

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/url-shortener-aws.git
git push -u origin main
```

### Automate deployments using GitHub Actions (optional)

- Add a GitHub Actions workflow to automate deployments.

## Future Enhancements

- User authentication for personalized URL tracking.
- Custom short URLs instead of auto-generated ones.
- Advanced analytics (geolocation, referrer tracking).

---

This project follows AWS best practices for scalability, security, and performance. 🚀
