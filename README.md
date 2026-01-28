# Lab-25-Jan-Task-8

# Create or Reuse a GitHub Repository
 1. Create a new GitHub repository or reuse an existing one
 2. Add a simple application or static HTML project to the repository
    - Add project file
    # Commands
       bash
       -mkdir Project
       -cd project
       -echo "Hello,World!">index.html
       -git init
       -git add .
       -git commit -m "Initial commit"
       -git remote add origin https://github.com/username/Project.git (github repo_url)
       -git push -u origin master
# Create a YAML Workflow File
 1. Navigate to the .github/workflows directory
 2. Create a new YAML file, e.g., ci.yml
 3. Define the CI pipeline in the YAML file
    #.github/workflows/ci.yaml
      name: CI pipeline
      on:
       push:
        branches:
          -master
        pull_request:
         branches:
          -master
       jobs:
        build:
         runs-on:ubuntu-latest
         steps:
         -name:checkout codde
          uses:actions/checkout@v2
         -name:Validate HTML
          run:|
           echo "Validating HTML.."
    
