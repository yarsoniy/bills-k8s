### Step 1: Prepare a kubernetes cluster and kubectl. And clone this repository

### Step 2: Install Nginx Ingress Controller
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.10.0/deploy/static/provider/cloud/deploy.yaml
```

### Step: Create a namespace for our project
```
kubectl create namespace bills
helm install bills-k8s ./helm/ --values ./helm/values.yaml -n bills
```

### Step 4: Create a secret for pulling images from private GitHub Container Registry
```
kubectl create secret docker-registry ghcr-pull-secret --docker-server=https://ghcr.io --docker-username=GITHUB_USERNAME --docker-password=GITHUB_ACCESS_TOKEN --docker-email=YOUR_EMAIL -n bills
```

### Step 5: Follow additional steps in this repositories:
https://github.com/yarsoniy/bills-web
https://github.com/yarsoniy/bills

### Step 6: Finish
Open http://localhost in your browser
