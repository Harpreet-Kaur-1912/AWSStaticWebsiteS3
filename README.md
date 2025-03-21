🌍 Website Deployment using GitHub Actions & Amazon S3

This repository contains a static website and a GitHub Actions workflow that automates the deployment of the website to an Amazon S3 bucket. The workflow ensures that any updates pushed to the repository are automatically deployed to S3, making website management seamless.

📁 Project Structure
graphql
Copy
Edit
├── .github/workflows/   # Contains GitHub Actions workflow files
│   ├── s3deploy.yml     # Workflow file for deploying to S3
│
├── Website/             # Folder containing website files
│   ├── index.html       # Main HTML file of the website
│   ├── README.md        # Project documentation
│
└── Other configuration files (if needed)

🚀 How It Works
Push Changes to GitHub

Make updates to the website files (e.g., index.html) and push them to the repository.
GitHub Actions Triggers Deployment

The s3deploy.yml workflow automatically runs whenever changes are pushed to the main branch.
It uploads the latest website files to the Amazon S3 bucket specified in the workflow file.
Website is Live on S3

Once the workflow completes successfully, the updated website will be accessible through the S3 bucket URL.
🛠 Setup Instructions
1️⃣ Create an Amazon S3 Bucket
Go to AWS Console → S3 → Create a new bucket.
Enable static website hosting under the Properties tab.
Copy the bucket name and region (you’ll need them for the workflow).
2️⃣ Set Up AWS Credentials in GitHub
In GitHub, go to Settings → Secrets and variables → Actions → New Repository Secret.
Add the following secrets:
AWS_ACCESS_KEY_ID → Your AWS access key
AWS_SECRET_ACCESS_KEY → Your AWS secret key
S3_BUCKET_NAME → Your S3 bucket name
AWS_REGION → Your S3 region (e.g., us-east-1)
3️⃣ Configure the s3deploy.yml File
The .github/workflows/s3deploy.yml file contains the deployment logic.
Ensure the bucket name and AWS region match your setup.
4️⃣ Deploy Your Website
Push changes to the main branch, and GitHub Actions will handle the deployment automatically! 🎉
🛡 Security Considerations
Never hardcode AWS credentials in the repository. Always use GitHub Secrets.
Enable Bucket Policy to make the website publicly accessible (if needed).
