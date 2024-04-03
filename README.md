### Step 1: Set up a fresh kubernetes cluster and kubectl. And clone this repository

### Step 2: Apply namespaces
```
kubectl apply -f ./namespaces/
```
### Step 3: Switch to *test* namespace that was just created
```
kubectl config set-context --current --namespace=test
```
### Step 2: Install Nginx Ingress Controller
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.10.0/deploy/static/provider/cloud/deploy.yaml
```
### Step 3: Apply other general configs configs
```
kubectl apply -f ./ingress/
kubectl apply -f ./mongo/
```

### Step 4: Create a secret for pulling images from private GitHub Container Registry
```
kubectl create secret docker-registry ghcr-pull-secret --docker-server=https://ghcr.io --docker-username=GITHUB_USERNAME --docker-password=GITHUB_ACCESS_TOKEN --docker-email=YOUR_EMAIL
```

### Step 5: Follow additional steps in this repositories:
https://github.com/yarsoniy/bills-web
https://github.com/yarsoniy/bills

### Step 6: Finish
Open http://localhost in your browser
