## EKS-deployment-using-Jenkins

This guide provides a step-by-step walkthrough for configuring Jenkins to deploy applications onto an Amazon EKS (Elastic Kubernetes Service) cluster. The deployment process encompasses the installation of essential tools within the Jenkins container, the setup of AWS authentication, and the customization of the Jenkinsfile to facilitate EKS cluster deployment.


# Eksctl cluster Installation

Establishing a Kubernetes cluster is simplified by utilizing eksctl, a powerful tool designed to streamline and optimize the setup process. By leveraging eksctl, this project ensures a straightforward and efficient deployment of the Kubernetes cluster. The installation guide, offering detailed steps, can be found in the AWS documentation at the following URL: https://eksctl.io/installation/. The Eks cluster was set on the server where the jenkins container is running

![1 create an eks cluster using eksctl](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/5e77a482-ce2b-4010-ac0b-f85b80241455)

![2   eks cluster on AWS](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/473c05d3-7516-4411-992f-54f0edffa8c0)


# Jenkins Server.

Within this project, the integration of a  preexisting jenkins server with a container built from a docker image was used for the continuous integration and continuous deployment (CI/CD) workflow.

![jenkin server](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/7264f62b-cc9a-41df-9229-5e14066ac979)



# Installation of Kubectl on Jenkins container

The installation of kubectl on the Jenkins server is indispensable as it functions as the command-line tool for interacting with Kubernetes clusters, including Amazon EKS (Elastic Kubernetes Service). This step is critical in the deployment process, as kubectl commands are utilized to proficiently manage and deploy applications to Kubernetes clusters. For detailed installation instructions, refer to the AWS documentation at the following URL: https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html

![3  Kubectl instalation within a jenkins container](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/be6ada2f-c184-403d-bc6d-9a11da7d0a45)



# Installation of iam-authenticator on Jenkins container

It is crucial to install iam-authenticator on the Jenkins container to establish secure authentication with AWS services. This installation is vital for enabling secure communication between Jenkins and Amazon EKS, ensuring protected access to the Kubernetes cluster. The authentication mechanism provided by iam-authenticator is an integral part of the overall project workflow, enhancing security measures and enabling proper interaction with AWS resources during the deployment process. For detailed installation instructions, refer to the following URL: https://weaveworks-gitops.awsworkshop.io/60_workshop_6_ml/00_prerequisites.md/50_install_aws_iam_auth.html


![4  aws-Iam-authenticator download inside the jenkins container](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/8e83b2ed-7ff4-424b-95c1-c633b51c46c7)


# Kubeconfig File

Generating the kubeconfig file is a crucial step in the project workflow, ensuring that the Jenkins user has the necessary permissions for secure access to the EKS cluster. This process involves creating the kubeconfig file, which integrates iam-authenticator for proper AWS Identity and Access Management (IAM) authentication. By following this step, a secure configuration is established, facilitating seamless communication between Jenkins and the EKS cluster during deployment. This is essential for maintaining security measures and ensuring smooth interaction with the Kubernetes environment, leveraging IAM for authentication. To create the kubeconfig file, refer to the following URL: https://docs.aws.amazon.com/eks/latest/userguide/create-kubeconfig.html

![5 creating a kubeconfig file within aws](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/6bccf05c-6c95-4569-a109-43e7466a4f3f)

Copy the kubeconfig file from the EKS cluster created earlier to the var/jenkins_home directory within the jenkins container 
check the  ownership of the kubeconfig file to confirm its owned by jenkins which enables seamless accessibility to the file by Jenkins,and also check the permissions of the file are given to the jenkins user.

![change ownership and permission rights on the kube config file](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/6bd27ec7-484e-4507-af5b-e71072437bd7)



# AWS Credentials on Jenkins

Integrating AWS credentials into Jenkins is a pivotal step in establishing secure and authenticated communication between Jenkins and AWS services. This ensures that Jenkins possesses the required access to AWS resources, thereby facilitating the deployment process. By supplying the AWS access key and secret access key, Jenkins obtains the necessary authorization to interact with the designated AWS account. This enhances the overall security and functionality of the CI/CD pipeline, contributing to a robust and reliable workflow.

![Screenshot from 2023-12-29 15-42-42](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/a52c0d98-9d99-4258-9938-701498b47905)

# Create a Jenkinsfile 

Created a new branch on an exisitng pipeline on Jenkins and also created a Jenkinsfile within the branch to include a deployment stage 

![Screenshot from 2023-12-29 15-47-18](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/62b2c048-3f00-4dcd-8119-94157f1674b1)

pushed from my local git repo to the git repo which automatically triggers and executes a branch within the multipipeline in Jenkins

![Screenshot from 2023-12-29 15-56-16](https://github.com/opeyemiagbadero/EKS-cluster-deployment-using-Jenkins/assets/79456052/67dcc78b-086c-4459-841e-e522f35786d8)


