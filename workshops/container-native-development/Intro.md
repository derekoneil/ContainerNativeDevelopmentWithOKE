# Workshop Introduction

## How to prepare for this Workshop

- To log issues and view the Lab Guide source, go to the [github oracle](https://github.com/oracle/learning-library/issues/new) repository.

- This version of the lab guides requires the use of an Oracle-provided VirtualBox or Cloud-hosted client image to use during the workshop. You can download the [VirtualBox image]() to run on your laptop, or switch to a different version of the lab guides using the dropdown menu at the top right of the page.

- Visit the [Workshop Interactive Labguide](https://launch.oracle.com/?container-native-development) for a visual overview of the workshop content.

## Container Native Application Development Workshop

Welcome to the Oracle Public Cloud Container Native Development workshop. This workshop will walk you through the process of moving an existing application into a containerized CI/CD pipeline and deploying it to a managed Kubernetes service in the Oracle Public Cloud.

You will take on 2 personas during the workshop. The Lead Developer Persona will be responsible for configuring the parts of the automated build and deploy process that involve details about the application itself. The DevOps Engineer Persona will configure the parts of the automation involving the Kubernetes infrastructure. To containerize and automate the building and deploying of this application you will make use of Wercker Pipelines, Oracle Container Registry, and Oracle Container Engine.

## Workshop Details

## Lab 100: Containerize Your Java Microservice

**Documentation**: [LabGuide100.md](LabGuide100.md)

### Objectives

- Create Wercker Application
  - Fork Java Application on GitHub
  - Create a Wercker account
  - Create Wercker application
- Create and Run Wercker Pipelines
  - Configure Pipelines and Workflow in Wercker
  - Define Wercker Build Pipeline
  - Set Environment Variables in Wercker
  - Define Wercker Publish Pipeline
  - Validate Workflow Execution

## Lab 200: Automate Deployment to Kubernetes

**Documentation**: [LabGuide200.md](LabGuide200.md)

### Objectives

- Create and Deploy to a Kubernetes Cluster
  - Set Up Oralce Cloud infrastructure
  - Provision Kubernetes Using Terraform
  - Configure and Run Wercker Deployment Pipelines
  - Deploy and Test the Product Catalog Application

## Lab 300: Make a Bug Fix to Your Java Microservice

**Documentation**: [LabGuide300.md](LabGuide300.md)

### Objectives

- Make a Bug Fix to Your Java Microservice
  - Modify Java Code and Commit to GitHub
  - Verify Execution of Wercker Workflow
  - Verify Deployment to Kubernetes
  - Test the Product Catalog Application

## Lab 400: Kubernetes Blue/Green Deployments

**Documentation**: [LabGuide400.md](LabGuide400.md)

### Objectives

- Perform a Blue/Green Deployment to Kubernetes
  - Update Existing Deployment and Service with Blue Color Labels
  - Validate Deployment Color In Kubernetes and Application
  - Increment Application Version and Switch Color to Green
  - Validate Blue Deployment Still Serves Traffic
  - Reconfigure Service to Switch to Green Deployment
  - Validate Green Deployment Now Serves Traffic

## Lab 500: Extend Your Application with a Function

**Documentation**: [LabGuide500.md](LabGuide500.md)

### Objectives

- Run Your Function Locally
  - Install Fn Server on Your Local Machine
  - Clone the Function Repository
  - Deploy the Function Locally
  - Test the Function Using curl
- Deploy Your Function to Fn on Kubernetes
  - Install Helm on Your Local Machine
  - Deploy Fn Server to Kubernetes Using Helm
  - Deploy Your Function to Fn Server on Kubernetes
  - Test Your Function in the Product Catalog
