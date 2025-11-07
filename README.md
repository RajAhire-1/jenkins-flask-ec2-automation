# Automated Flask Authentication Deployment
**Jenkins CI/CD Pipeline with AWS EC2**

## 📋 Project Overview
A complete CI/CD pipeline that automatically deploys a Flask-based login/signup application to AWS EC2 using Jenkins. Every code push to GitHub triggers an automated deployment process.

## 🚀 Live Application
**Access the deployed application:**  
`http://3.110.103.246:5000`

## 🛠️ Technology Stack
- **Backend:** Python Flask
- **Frontend:** HTML, CSS, JavaScript
- **Database:** SQLite3
- **CI/CD:** Jenkins
- **Cloud:** AWS EC2
- **Version Control:** GitHub

## 🔄 Automated Workflow

### 1. Code Development
- Flask application with animated login/signup UI
- User authentication with secure password hashing
- SQLite database for user management

### 2. Version Control
```bash
git add .
git commit -m "Update application"
git push origin master
```

### 3. Jenkins Automation
- Monitors GitHub repository for changes
- Automatically triggers deployment pipeline
- Deploys to AWS EC2 instance

### 4. Deployment Process
- Copies files to EC2 instance via SSH
- Installs Python dependencies
- Runs Flask application on port 5000

## ⚙️ Pipeline Configuration

### Jenkinsfile Structure
```groovy
pipeline {
    agent any
    environment {
        SSH_CRED = 'check-ssh-key'
        SERVER_IP = '172.31.12.114'
        REMOTE_USER = 'ubuntu'
        APP_DIR = '/home/ubuntu/pythonapp'
    }
    
    stages {
        stage('Clone Repo') {
            // Pulls code from GitHub
        }
        stage('Deploy to Server') {
            // Copies files to EC2
        }
        stage('Install & Run App') {
            // Sets up environment and starts application
        }
    }
}
```

### Jenkins Setup
- **SSH Credential ID:** `check-ssh-key`
- **Target Server:** `172.31.12.114` (EC2 Private IP)
- **Application Directory:** `/home/ubuntu/pythonapp`

## 📁 Project Structure
```
pythonapp/
├── app.py              # Flask application
├── requirements.txt    # Python dependencies
├── templates/         # HTML templates
├── static/           # CSS/JS assets
├── test/             # Test files
├── Jenkinsfile       # CI/CD pipeline
└── README.md        # Documentation
```

## 🔧 Quick Start

### Manual Deployment
```bash
# Clone repository
git clone https://github.com/RajAhire-1/pythonapp.git
cd pythonapp

# Setup virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run application
python3 app.py --host=0.0.0.0 --port=5000
```

## 🌐 Access Points
- **Application URL:** http://3.110.103.246:5000
- **EC2 Public IP:** 3.110.103.246
- **EC2 Private IP:** 172.31.12.114

## ✅ Features
- ✅ Automated CI/CD pipeline
- ✅ Modern animated UI
- ✅ User authentication system
- ✅ Secure password hashing
- ✅ SQLite database integration
- ✅ Background process management

## 🎯 Result
After each `git push` to master:
- Jenkins automatically detects changes
- Deploys latest code to EC2 instance
- Application updates without manual intervention
- Zero downtime deployment

