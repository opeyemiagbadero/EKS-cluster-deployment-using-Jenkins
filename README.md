## EKS-deployment-using-Jenkins

This guide provides a step-by-step walkthrough for configuring Jenkins to deploy applications onto an Amazon EKS (Elastic Kubernetes Service) cluster. The deployment process encompasses the installation of essential tools within the Jenkins container, the setup of AWS authentication, and the customization of the Jenkinsfile to facilitate EKS cluster deployment.

# Eksctl cluster Installation

Establishing a Kubernetes cluster is simplified by utilizing eksctl, a powerful tool designed to streamline and optimize the setup process. By leveraging eksctl, this project ensures a straightforward and efficient deployment of the Kubernetes cluster. The installation guide, offering detailed steps, can be found in the AWS documentation at the following URL: https://eksctl.io/installation/



# Jenkins Server.

Within this project, the integration of a  preexisting jenkins server with a container built from a docker image was used for the continuous integration and continuous deployment (CI/CD) workflow.



# Installation of Kubectl on Jenkins container

The installation of kubectl on the Jenkins server is indispensable as it functions as the command-line tool for interacting with Kubernetes clusters, including Amazon EKS (Elastic Kubernetes Service). This step is critical in the deployment process, as kubectl commands are utilized to proficiently manage and deploy applications to Kubernetes clusters. For detailed installation instructions, refer to the AWS documentation at the following URL: https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html


# Installation of iam-authenticator on Jenkins container

It is crucial to install iam-authenticator on the Jenkins container to establish secure authentication with AWS services. This installation is vital for enabling secure communication between Jenkins and Amazon EKS, ensuring protected access to the Kubernetes cluster. The authentication mechanism provided by iam-authenticator is an integral part of the overall project workflow, enhancing security measures and enabling proper interaction with AWS resources during the deployment process. For detailed installation instructions, refer to the following URL: https://weaveworks-gitops.awsworkshop.io/60_workshop_6_ml/00_prerequisites.md/50_install_aws_iam_auth.html

# Kubeconfig File

Generating the kubeconfig file is a crucial step in the project workflow, ensuring that the Jenkins user has the necessary permissions for secure access to the EKS cluster. This process involves creating the kubeconfig file, which integrates iam-authenticator for proper AWS Identity and Access Management (IAM) authentication. By following this step, a secure configuration is established, facilitating seamless communication between Jenkins and the EKS cluster during deployment. This is essential for maintaining security measures and ensuring smooth interaction with the Kubernetes environment, leveraging IAM for authentication. To create the kubeconfig file, refer to the following URL: https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html

