# Lab-25-Jan-Task-8

# CI Pipeline Documentation – Jenkins (Local)

1. Prerequisites
  -Jenkins installed (Local VM / EC2 / WSL)
  -Java 11 or 17 installed
  -Git installed
  -GitHub repository with a simple project (static HTML / Java / Node.js)
  -Jenkins admin access

2. Jenkins Installation (Summary)
   # COMMANDS
   bash
   sudo apt update
   sudo apt install openjdk-17-jdk -y
   wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
   sudo sh -c 'echo deb https://pkg.jenkins.io/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
   sudo apt update
   sudo apt install jenkins -y
   sudo systemctl start jenkins

    Access Jenkins:
     http://<server-ip>:8080

3. Repository Structure
       my-ci-project/
       cd my-ci-project
        index.html
        Jenkinsfile

4. Create a New Jenkins Job
   - Open Jenkins in your web browser: http://localhost:8080 (default port)
   - Click on "New Item" to create a new job
   - Choose "Freestyle project" or "Pipeline" depending on your needs
      # Pipeline Job
   - Login to Jenkins Dashboard
   - Click New Item
     Enter job name → select Pipeline
     Under Pipeline section:
     Definition: Pipeline script from SCM
     SCM: Git
     Repository URL: GitHub repo URL
     Branch: main
       Save

5. Configure the Job
   - Enter a job name and description
   - Configure the source code management (SCM) system, e.g., Git
   - Specify the build triggers, e.g., poll SCM or trigger remotely

6. Add Build Steps
   - Add build steps to execute shell commands, run scripts, or deploy applications
   - Use Jenkins plugins to integrate with other tools and services
      # Basic Jenkinsfile
pipeline {
   agent any
      stages {
        stage('Checkout Code') {
          steps {
             git branch: 'main', url: 'https://github.com/username/my-ci-project.git'
          }
       }
      stage('Validate Code') {
        steps {
             sh '''
             echo "Jenkins CI pipeline triggered"
             ls -l
             '''
          }
        }
     }
 }



     
