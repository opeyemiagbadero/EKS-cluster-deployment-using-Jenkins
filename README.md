## EKS-deployment-using-Jenkins

This guide provides a step-by-step walkthrough for configuring Jenkins to deploy applications onto an Amazon EKS (Elastic Kubernetes Service) cluster. The deployment process encompasses the installation of essential tools within the Jenkins container, the setup of AWS authentication, and the customization of the Jenkinsfile to facilitate EKS cluster deployment.

# Eksctl cluster Installation

Establishing a Kubernetes cluster is simplified by utilizing eksctl, a powerful tool designed to streamline and optimize the setup process. By leveraging eksctl, this project ensures a straightforward and efficient deployment of the Kubernetes cluster. The installation guide, offering detailed steps, can be found in the AWS documentation at the following URL: https://eksctl.io/installation/



# Jenkins Server.

Within this project, the integration of a  preexisting jenkins server with a container built from a docker image was used for the continuous integration and continuous deployment (CI/CD) workflow.





The installation of kubectl on the Jenkins server is indispensable as it functions as the command-line tool for interacting with Kubernetes clusters, including Amazon EKS (Elastic Kubernetes Service). This step is critical in the deployment process, as kubectl commands are utilized to proficiently manage and deploy applications to Kubernetes clusters.

For detailed installation instructions, refer to the AWS documentation at the following URL: https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html




