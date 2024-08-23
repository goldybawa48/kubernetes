# Architecture of Kubernetes

**In a kubernetes there is one master node which is called control plan and another is worker node it can be a one or more than one in one master node. Components of master node (API Server, etcd, Scheduler, Controller Manager) and Components of worker node (Kubelet, Kube Proxy, Container Runtime, Pod)**

## Diagram

![Screenshot from 2024-08-12 17-19-00](https://github.com/user-attachments/assets/1de3ce49-307c-44f4-95dc-310b6b7a3c5f)

![alt text](image.png)

## Explanation 

**In kubernetes we have two nodes one is worker nod and the second is master node.**

### Master node

**The master node controls and manages the cluster. It consists of API server, etcd, controller manager and Scheduler.**

- **API server** - All operations such as scheduling and scaling pass through this component. It Acts as the front-end, serving the Kubernetes API.

- **etcd** - A distributed key-value store that holds the cluster state and configuration data

- **controller** - The Controller Manager in Kubernetes is like a supervisor who watches over different parts of the system to make sure everything is working as expected. If something goes wrong, the Controller Manager takes action to fix it and bring things back to normal.

- **Scheduler** - Assigns workloads (in the form of pods) to worker nodes based on resource availability and other factors.


### Worker node

**The worker nodes are where your containerized applications actually run. Each node contains kubelet, kube-proxy and container runtime.**

- **kubelet** - The agent that ensures containers are running in pods on a node. It interacts with the API Server to receive tasks and ensures pod states are as expected.

- **kube-proxy** - Handles network communication between pods and external services, enabling networking in the cluster.

- **container runtime** - Responsible for pulling container images and running containers in pods.