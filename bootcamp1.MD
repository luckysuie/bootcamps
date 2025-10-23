## Title: Deploying a Java spring boot application to AKS using Jenkins via Maven, SonarQube, Docker, Trivy, ACR
1. Fork the repository https://github.com/spring-projects/spring-petclinic
 to your GitHub account

Clone the forked repository to your local system and open it in Visual Studio Code

Create a resource group named demo11 in Azure

Create an Ubuntu virtual machine in the demo11 resource group with username azureuser, at least 2 CPUs, and 4GB RAM, with all ports open

In Microsoft Entra ID, register a new application named lucky

In the lucky app registration, create a client secret and note down the Application (client) ID, Directory (tenant) ID, and secret value

Assign the Owner role to the lucky application under your Azure subscription’s IAM settings

Connect to the VM using SSH

Update the system packages

Create a file named installations.sh and paste the script from the provided GitHub link

Run the installations.sh file to install Git, Java, Maven, Jenkins, Docker, Trivy, Azure CLI, and kubectl

Log in to Azure on the VM using az login --use-device-code

Access Jenkins in the browser using the VM public IP and port 8080

Retrieve the initial admin password from /var/lib/jenkins/secrets/initialAdminPassword

Complete the Jenkins setup and create an admin user account

Install Jenkins plugins: Pipeline Stage View, Maven Integration, and SonarQube Scanner

Create a SonarCloud account and generate an authentication token

In Jenkins, add SonarCloud credentials under Manage Jenkins > Credentials > Global

In Jenkins, add Azure credentials under Manage Jenkins > Credentials > Global

Create an Azure Container Registry named luckyregistry in the demo11 resource group

Create an AKS cluster named lucky-aks-cluster11 in the demo11 resource group with one node

Configure kubectl to connect to the AKS cluster using az aks get-credentials

Create a Kubernetes secret for ACR to allow image pulling from the registry

In GitHub, configure a webhook for your forked repository pointing to http://yourvmip:8080/github-webhook/

In Jenkins, create a new pipeline project and configure it to use pipeline script from SCM (Git)

Set the GitHub repository URL and branch name in the pipeline configuration

Enable GitHub hook trigger for GITScm polling in Jenkins

In Visual Studio Code, create or edit the Jenkinsfile in your repository

Define pipeline stages for Git checkout, Maven validate, compile, test, package, SonarCloud analysis, Docker build, Trivy image scan, push image to ACR, and deployment to AKS

Commit and push the Jenkinsfile to your GitHub repository

Run the Jenkins pipeline manually or by triggering a Git push

Verify that the application is deployed to the AKS cluster

Get the load balancer IP of your service from AKS and open it in the browser to see the application page
