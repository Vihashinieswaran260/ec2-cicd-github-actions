EC2 CI/CD Deployment Using GitHub Actions

This project demonstrates a fully automated CI/CD pipeline that deploys a static webpage to an Amazon EC2 instance whenever changes are pushed to GitHub. The setup uses GitHub Actions for automation, SSH for secure deployment, and EC2 User Data to provision the server during launch.

🚀 Project Overview

This project covers the complete workflow of deploying a website using AWS and GitHub automation:

Launching an EC2 instance using AWS Free Tier

Using User Data to automatically install Apache and deploy the initial webpage

Storing sensitive values safely using GitHub Secrets

Running a GitHub Actions pipeline to deploy updated files instantly

Achieving hands-free deployment with zero manual SSH login

🛠 Technologies Used

| Component                | Purpose                               |
| ------------------------ | ------------------------------------- |
| AWS EC2                  | Hosts the application                 |
| Amazon Linux 2           | Operating system for the EC2 instance |
| Apache (httpd)           | Web server to serve the application   |
| GitHub Actions           | CI/CD automation                      |
| SSH + GitHub Secrets     | Secure communication with EC2         |
| YAML Workflow            | Defines automated deployment steps    |

📂 Project Structure

ec2-cicd-github-actions/
│── index.html
│── README.md
│── .github/
│     └── workflows/
│           └── deploy.yml
│── screenshots/   (proof of deployment)

🔐 GitHub Secrets Used

| Secret Name     | Description                                 |
| --------------- | ------------------------------------------- |
| EC2_HOST        | Public IP address of the EC2 instance       |
| EC2_SSH_KEY     | Private PEM key used for SSH authentication |

⚙️ CI/CD Workflow Explanation

Whenever a commit is pushed to the main branch, GitHub Actions automatically:

Pulls the latest source code

Connects to the EC2 instance using SSH

Deletes the existing /var/www/html/index.html

Uploads the new version of index.html

Restarts the Apache server

Updates the live website instantly

This ensures continuous integration and continuous deployment with no manual effort.

🖥 Architecture Diagram

     ┌──────────────────┐
     │ Developer Pushes │
     │  Code to GitHub  │
     └───────┬──────────┘
             │ Triggers Workflow
             ▼
   ┌─────────────────────────┐
   │     GitHub Actions      │
   │   CI/CD Deployment      │
   └───────┬─────────────────┘
           │ SSH Deploy
           ▼
   ┌─────────────────────────┐
   │      AWS EC2 Server     │
   │ Apache serves website   │
   └──────────┬──────────────┘
              ▼
      http://13.221.63.18/

📸 Screenshots (Proof of Deployment)

Included inside the screenshots/ folder:

EC2 instance running

Public IP webpage output

GitHub repository structure

GitHub Secrets configuration

Workflow YAML file

Successful Actions run

Final deployed webpage

✔️ Final Result

Whenever index.html is updated on GitHub:

➡️ A new deployment automatically runs
➡️ The updated file is pushed to EC2
➡️ Apache restarts
➡️ The new webpage appears instantly in the browser

This project demonstrates a clean, real-world CI/CD pipeline using GitHub Actions and AWS.

