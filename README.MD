# Sample Kubernetes Application

This repository contains a sample Kubernetes application. Classic 3 tier application setup emulating web, app and database.

Using Nic Jacksons excellent [Fake Service](https://github.com/nicholasjackson/fake-service)


## Test
*Using WSL2 on Windows 10*

Setup k3d and create a cluster in WSL2. Requires Docker to be setup.

```bash
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
k3d cluster create --api-port 6550 -p "8081:80@loadbalancer"
```

Deploy application. Uses default k3d ingress / Traefik

```bash
kubectl apply -f db.yaml
kubectl apply -f app.yaml
kubectl apply -f web.yaml
```