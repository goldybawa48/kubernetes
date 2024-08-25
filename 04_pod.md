# Pod

**In Kubernetes, a Pod is the smallest and most basic deployable unit. It represents a single instance of a running process in your cluster and can contain one or more containers that are tightly coupled and share the same resources.**

## Key Aspects of a Pod

- **Multiple Containers** :- A pod can contain one or more containers (usually Docker containers) that share the same network namespace, meaning they can communicate with each other using localhost and share storage volumes. In most cases, a pod runs a single container, but in scenarios where multiple containers need to work together (like a logging sidecar container), they are deployed in the same pod.

- **Shared Resources** :- Containers within a pod share the same storage, IP address, port space, and configuration settings (such as secrets and environment variables).

- **Networking** :- Each pod gets its own IP address in the cluster. Containers within the same pod can communicate with each other over localhost, while communication between pods occurs over the network.

- **Pod States** :- Pods can be in various states such as Running, Pending, Succeeded, Failed, and CrashLoopBackOff, indicating the current health or activity of the pod.

## Let's Create first pod

- Run this command to run a single pod of nginx.

```bash
kubectl run nginx-pod --image=nginx
```

- To verify run this command.

```bash
kubectl get pods
```

- To delete this pod.

```bash
kubectl delete pod <POD-NAME>
```

## States 

**Now let's talk about states of pod**

- **Running** :- The Pod has been bound to a node, and all the containers in the Pod have been created and are running.

- **Pending** :- The Pod has been accepted by the Kubernetes cluster but one or more of its containers are not yet running.

  **cause** :- This could be because the image is still being pulled, or the Pod is waiting for resources like CPU or memory to be scheduled on a node. Image pull issues, Resource limitations.

- **Succeeded** :-  All containers in the Pod have successfully terminated, and they will not be restarted.

  **uses** :- For Pods that run batch jobs, one-time scripts, or tasks that complete successfully and do not need to run again.

- **Failed** :- All containers in the Pod have terminated, and at least one container has exited with a non-zero status (failure).

  **cause** :- any container in the pod is failled to start because of configuration issue or insufficient resources.

- **CrashLoopBackOff** :- The Pod is in a cycle of starting, failing, and then restarting.

  **condition** :- Kubernetes attempts to restart the containers in the Pod, but they keep crashing. This results in a "CrashLoopBackOff" state, meaning Kubernetes will wait before attempting another restart.

  **cause**:-

  Incorrect configuration or environment variables.

  Application-level errors.

  Resource constraints (such as memory or CPU limits).

- **Unknown** :- The state of the Pod is unknown to the Kubernetes control plane.

   **Reason** :- This typically happens when the node hosting the Pod cannot be contacted e.g., network partitioning, node crash.

   **Cause** :- Node or network failures, Miscommunication between the Kubernetes API server and the node

- **Terminating** :- The Pod is in the process of shutting down and all containers are being terminated. This occurs when a pod is being deleted.

  **Condition** :- The Pod is gracefully shutting down, giving containers a chance to stop properly before being forcefully terminated.

- **Completed** :- Similar to Succeeded, the Pod has successfully completed all tasks, but this state is explicitly shown for short-lived Pods that do not restart.

  **Condition** :- All containers have successfully completed, and the Pod remains in this state unless explicitly cleaned up Often seen in jobs or one-time tasks.