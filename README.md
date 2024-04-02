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
kubectl apply -f ./mongo/
```

### Step 3: Add a new record to your /etc/hosts
```
127.0.0.1       bills.loc
```

### Step 4: Create a secret for pulling images from private GitHub Container Registry
```
kubectl create secret docker-registry ghcr-pull-secret --docker-server=https://ghcr.io --docker-username=GITHUB_USERNAME --docker-password=GITHUB_ACCESS_TOKEN --docker-email=YOUR_EMAIL
```

### Step 5: Follow additional steps in this repositories:
https://github.com/yarsoniy/bills-web
https://github.com/yarsoniy/bills

### Step 6: Finish
Open http://bills.loc in your browser
