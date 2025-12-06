EC2 CI/CD Deployment Using GitHub Actions

This project showcases a fully automated CI/CD pipeline that deploys a static webpage to an Amazon EC2 instance whenever changes are pushed to GitHub. The pipeline uses GitHub Actions for automation, SSH for secure deployment, and EC2 User Data for initial server setup.

🚀 Project Overview

This project demonstrates:

Automatic EC2 provisioning using AWS Free Tier

User Data script to install Apache and deploy the first version of the website

Secure authentication using GitHub Secrets

Automated deployments triggered by GitHub Actions

Zero manual login to EC2 after initial setup

🛠 Technologies Used
Component	Purpose
AWS EC2	Hosting the website
Amazon Linux 2	Base OS for server
Apache (httpd)	Web server
GitHub Actions	CI/CD workflow
SSH + Secrets	Secure automated login
YAML Workflow	Deployment automation
📂 Project Structure
ec2-cicd-github-actions/
│── index.html
│── README.md
│── .github/workflows/deploy.yml
│── screenshots/  (deployment proof)
🔐 GitHub Secrets Used
Secret Name	Purpose
EC2_HOST	Public IP of EC2 instance
EC2_SSH_KEY	Private key (PEM) for SSH authentication
⚙️ CI/CD Workflow Explanation

Whenever a commit is pushed to the main branch:

GitHub Actions pulls the latest code

Connects to the EC2 instance using SSH

Removes the old /var/www/html/index.html

Uploads the new index.html

Restarts Apache

Website updates instantly

🖥 Architecture Diagram
         ┌──────────────────┐
         │ Developer Pushes │
         │  Code to GitHub  │
         └───────┬──────────┘
                 │ (Triggers)
                 ▼
        ┌──────────────────────┐
        │   GitHub Actions     │
        │  CI/CD Workflow      │
        └───────┬──────────────┘
                │ SSH Deploy
                ▼
     ┌────────────────────────────┐
     │       AWS EC2 Server       │
     │ Apache serves index.html   │
     └───────────┬────────────────┘
                 ▼
       User visits website via  
      http://EC2-Public-IP

📸 Screenshots (Proof of Deployment)

All screenshots are available in the screenshots/ folder:

EC2 Instance running

Public IP webpage output

GitHub Repository

GitHub Actions workflow

GitHub Secrets

Successful deployment

Final website output

✔️ Final Result

Updating index.html on GitHub automatically deploys the new version to EC2 within seconds — without logging into the server.

This demonstrates a real, working CI/CD pipeline using GitHub Actions and AWS.

🧑‍💻 Interview Explanation (Short & Strong Answer)

If an interviewer asks:

“Explain your CI/CD Project.”

Say this:

I built a CI/CD pipeline where pushing code to GitHub automatically deploys the latest version of a website to an EC2 instance.
EC2 installs Apache via User Data, and GitHub Actions connects through SSH using secrets.
The workflow replaces the old HTML file and restarts Apache, making deployment fully automated with zero manual steps.

Short, clear, professional.

📄 Resume Bullet Points (Paste These)

EC2 CI/CD Automation using GitHub Actions

Developed an automated CI/CD pipeline to deploy a static website to an AWS EC2 server using GitHub Actions.

Configured EC2 User Data for automatic Apache setup and initial deployment.

Implemented secure SSH-based deployment using GitHub Secrets for key management.

Automated end-to-end deployment workflow, enabling instant updates on every commit.
