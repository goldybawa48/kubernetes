# Edit the resource

**I created a pod with image of nginx now i want to change the image of the pod**

## How to do

- this is my yaml file of pod which is running.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: firstpod
  labels:
    env: test
spec:
  containers:
    - name: firstpodcontainer
      image: nginx
```

- Now change the name of image.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: firstpod
  labels:
    env: test
spec:
  containers:
    - name: firstpodcontainer
      image: httpd
```

- Velidate with dry run.

```bash
kubectl apply -f pod.yaml --dry-run=client
```

- Now run without dry run.

```bash
kubectl apply -f pod.yaml
```

- Now your image is chnaged in the pod

- same you can do with deployment and other resources configration.