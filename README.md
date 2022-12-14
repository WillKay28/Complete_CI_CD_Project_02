# Complete_CI_CD_Project_02

In this project, I create an automated Docker CI pipeline that fetches java code from a repo on GitHub into Jenkins, builds and performs unit test using Maven, performs code analysis for bugs and code smells using SonarQube Scanner and builds the artifact. A docker image of the the artifact is built and published to Amazon ECR (Could be replaced with Google Container Registry (GCR), Azure Registry Servers, DockerHub, etc.). 


Included in the pipeline is a post-installation step that sends notifications to dev indicating whether the pipeline executed successfully or failed using Slack Notification.

I created 3 EC2 Linux Instance Servers for:

Jenkins (Ubuntu)
SonarQube (Ubuntu)
Nexus OSS (CentOS)

Process:
- Install docker engine in Jenkins
  * Add Jenkins user to docker group & reboot
- Install AWS CLI
- Create IAM User
- Create ECR repo on AWS
- Install the ff plugins in Jenkins
  * ECR
  * Docker pipeline
  * AWS SDK for Credentials
- Store AWS Credentials in Jenkins
- Run the pipeline
