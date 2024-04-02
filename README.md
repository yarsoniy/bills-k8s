### Step 1: Set up a kubernetes cluster and kubectl. And clone this repository

### Step 2: Apply namespaces
```
kubectl apply -f ./namespaces/
```
### Step 3: Switch to *test* namespace that was just created
```
kubectl config set-context --current --namespace=test
```
### Step 2: Apply other general configs configs
```
kubectl apply -f ./ingress/
```

### Step: Create a secret for private ghcr
```
kubectl create secret docker-registry ghcr-pull-secret --docker-server=https://ghcr.io --docker-username=GITHUB_USERNAME --docker-password=GITHUB_ACCESS_TOKEN --docker-email=YOUR_EMAIL
```
