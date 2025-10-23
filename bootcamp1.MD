## Title: Deploying a Java spring boot application to AKS using Jenkins via Maven, SonarQube, Docker, Trivy, ACR
1. Fork the repository https://github.com/spring-projects/spring-petclinic
 to your GitHub account

2. Clone the forked repository to your local system and open it in Visual Studio Code

3. Create a resource group named demo11 in Azure

4. Create an Ubuntu virtual machine in the demo11 resource group with username azureuser, at least 2 CPUs, and 4GB RAM, with all ports open

5. In Microsoft Entra ID, register a new application named lucky

6. In the lucky app registration, create a client secret and note down the Application (client) ID, Directory (tenant) ID, and secret value

7. Assign the Owner role to the lucky application under your Azure subscription’s IAM settings

8. Connect to the VM using SSH

9. Update the system packages

10. Create a file named installations.sh and paste the script from the provided GitHub link

11. Run the installations.sh file to install Git, Java, Maven, Jenkins, Docker, Trivy, Azure CLI, and kubectl

12. Log in to Azure on the VM using az login --use-device-code

13. Access Jenkins in the browser using the VM public IP and port 8080

14. Retrieve the initial admin password from /var/lib/jenkins/secrets/initialAdminPassword

15. Complete the Jenkins setup and create an admin user account

16. Install Jenkins plugins: Pipeline Stage View, Maven Integration, and SonarQube Scanner

17. Create a SonarCloud account and generate an authentication token

18. In Jenkins, add SonarCloud credentials under Manage Jenkins > Credentials > Global

19. In Jenkins, add Azure credentials under Manage Jenkins > Credentials > Global

20. Create an Azure Container Registry named luckyregistry in the demo11 resource group

21. Create an AKS cluster named lucky-aks-cluster11 in the demo11 resource group with one node

22. Configure kubectl to connect to the AKS cluster using az aks get-credentials

23. Create a Kubernetes secret for ACR to allow image pulling from the registry

24. In GitHub, configure a webhook for your forked repository pointing to http://yourvmip:8080/github-webhook/

25. In Jenkins, create a new pipeline project and configure it to use pipeline script from SCM (Git)

26. Set the GitHub repository URL and branch name in the pipeline configuration

27. Enable GitHub hook trigger for GITScm polling in Jenkins

28. In Visual Studio Code, create or edit the Jenkinsfile in your repository

29. Define pipeline stages for Git checkout, Maven validate, compile, test, package, SonarCloud analysis, Docker build, Trivy image scan, push image to ACR, and deployment to AKS

30. Commit and push the Jenkinsfile to your GitHub repository

31. Run the Jenkins pipeline manually or by triggering a Git push

32. Verify that the application is deployed to the AKS cluster

33. Get the load balancer IP of your service from AKS and open it in the browser to see the application page
