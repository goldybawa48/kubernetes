# Minikube

**Minikube is an open-source tool that enables you to run a single-node Kubernetes cluster on your local machine. It's designed to be a lightweight and easy-to-use solution for developers and DevOps engineers who want to learn, develop, and test Kubernetes applications in a local environment without needing to set up a full-scale Kubernetes cluster.**

## Installation

- Run the below commands to install minikube.

    ```bash
    sudo apt-get update
    sudo apt-get install -y curl
    sudo apt-get install -y docker.io
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    sudo install minikube-linux-amd64 /usr/local/bin/minikube
    minikube start --driver=docker

- Now run `minikube status`this commands your output have to look like this

  ![Screenshot from 2024-08-11 14-24-03](https://github.com/user-attachments/assets/5ed22a67-f27f-40cd-bca1-b25a81fef8dc)

# Kubectl

**kubectl is the command-line tool used to interact with a Kubernetes cluster. It allows you to manage and operate Kubernetes resources and applications. With kubectl, you can perform a wide range of tasks, such as deploying applications, inspecting and managing cluster resources, and viewing logs.**

## Installation

- Run the below commands to install kubectl.

    ```bash
    curl -LO "https://dl.k8s.io/release/v1.26.3/bin/linux/amd64/kubectl"
    chmod +x ./kubectl
    sudo mv ./kubectl /usr/local/bin/kubectl

- Now run `kubectl version --client --short`this commands your output have to look like this

   ![Screenshot from 2024-08-12 16-11-15](https://github.com/user-attachments/assets/425aa6ef-e954-4ece-887a-04f7d3ec1371)