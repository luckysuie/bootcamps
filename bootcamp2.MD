## Title: Deploying a Java Spring Boot Application to AKS using Azure DevOps with Maven, SonarQube, Docker, Trivy, and ACR
Raw Steps:
1.	Create a new project named pipeline-8 in Azure DevOps.
2.	Navigate to Repos and import the repository https://github.com/bkrrajmali/enahanced-petclinc-springboot.
3.	Log in to SonarCloud using your GitHub account.
4.	Create an organization named JavaOrganization and a project named javanalysis in SonarCloud.
5.	Generate a SonarCloud token and note down the token, project key, project name, organization name, and organization key.
6.	In Azure DevOps, create a service connection for SonarCloud using the generated token.
7.	In Azure DevOps project settings, create a service connection using Azure Resource Manager.
8.	Open Azure Cloud Shell and create a resource group.
9.	Create an Azure Container Registry (ACR) inside that resource group and enable admin user access.
10.	Create an Azure Kubernetes Service (AKS) cluster in the same resource group.
11.	Create a Kubernetes secret to authenticate between ACR and AKS.
12.	In Azure DevOps, create a service connection for ACR.
13.	Configure the CI pipeline with the following stages:
  o	Install Java and Maven.
  o	Prepare SonarCloud analysis.
  o	Run Maven build with SonarQube scan.
  o	Publish SonarCloud analysis report.
  o	Build and push Docker image to ACR.
  o	Perform Trivy vulnerability scan on the Docker image and publish the report.
14.	Configure the CD pipeline with the following stages:
  o	Connect to AKS using Azure Resource Manager service connection.
  o	Deploy Kubernetes manifests to AKS.
15.	Validate pipeline execution and verify outputs:
  o	Successful SonarCloud analysis report.
  o	Trivy vulnerability report generation.
  o	Deployed web application accessible via AKS public endpoint.


