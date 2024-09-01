# Diffrence in kubectl apply and kubectl create

**this both commands aqre used to create resource from the menifest files. but they are diffrent from each other.**

`kubectl apply -f file.yaml`

`kubectl create -f file.yaml`

## apply

**Used for declarative management of Kubernetes resources. It compares the current state of the cluster with the desired state defined in the manifest file and applies any changes needed to achieve the desired state.**

- If the resource exists, it will be updated to match the manifest.

- Supports incremental changes over time (e.g., updating fields of an existing resource).

## create

**Used for imperative management of Kubernetes resources. It creates a new resource from the manifest file.**

- If the resource already exists, the command will fail with an error indicating that the resource already exists.

- Does not support updating existing resources.

- we can edit these resources with edit command

`kubectl edit <resource> <resource-name>`