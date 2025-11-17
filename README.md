🚀 Portfolio Website – CI/CD with GitHub Actions & AWS S3

This project demonstrates a fully automated CI/CD pipeline using GitHub Actions to deploy a static portfolio website to **AWS S3**.  
Whenever code is pushed to the `master` branch, the latest version is automatically deployed.

📂 Project Structure
├── index.html
├── style.css
├── script.js
└── .github/workflows/main.yml

🛠️  Tech Stack
- HTML, CSS, JavaScript – Portfolio website  
- GitHub Actions – CI/CD automation  
- AWS S3 – Static hosting  
- AWS IAM – Secure authentication

⚙️  CI/CD Workflow
 The CI/CD pipeline performs the following steps:

1. Checkout repository  
2. Configure AWS credentials using GitHub Secrets  
3. Upload website files to S3 using `aws s3 sync`  
4. Delete old files  
5. Exclude unnecessary folders (`.git`, `.github`, `.yml`)

🔒 AWS IAM Permissions
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:PutObject",
        "s3:DeleteObject",
        "s3:ListBucket"
      ],
      "Resource": [
        "arn:aws:s3:::kishan-project1",
        "arn:aws:s3:::kishan-project1/*"
      ]
    }
  ]
}

🌐 Deployment
git add .
git commit -m "update portfolio"
git push origin main

S3 URL
http://kishan-project1.s3-website-us-east-1.amazonaws.com/

