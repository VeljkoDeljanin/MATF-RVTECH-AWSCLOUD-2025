# EV Chargers Map – Serverless LocalStack Demo
This project is a serverless web application that displays EV charging stations on a map, using data from Open Charge Map. The backend is built with AWS Lambda, API Gateway, and DynamoDB, all running locally via LocalStack, while the frontend is a simple static website hosted on S3 (LocalStack).

## Prerequisites
- Node.js
- Docker & Docker Compose
- Serverless Framework
- AWS CLI
- LocalStack CLI

## Environment Variables
Create a .env file based on .env.example:
```
cp .env.example .env
```
Fill in your Open Charge Map API key:
```
OCM_API_KEY=your_real_api_key_here
```

## Running the project
1. Start LocalStack
    ```
    docker compose up -d
    ```

2. Install dependencies
    ```
    npm install
    ```

3. Deploy serverless stack
    ```
    serverless deploy
    ```

4. Upload the web/ folder to S3
    ```
    awslocal s3 sync ./web s3://punjaci-website
    ```

5. Open in browser:
http://punjaci-website.s3-website.localhost.localstack.cloud:4566
