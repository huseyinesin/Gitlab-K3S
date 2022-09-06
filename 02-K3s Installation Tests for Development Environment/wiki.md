# Rancher's k3s - Resource usage test

## Install and Update Ubuntu system
Launch your server and agent nodes with the ubuntu image 
With your servers installed with Ubuntu image, update and upgrade them

```bash
sudo hostname master
bash
sudo apt update
sudo apt -y upgrade

```
## Install K3s Master and Worker 
Install Master

```bash
curl -sfL https://get.k3s.io | sh -s - --no-deploy traefik --write-kubeconfig-mode 644 --node-name k3s-master-01
```
To check if the service installed successfully, you can use

```bash
systemctl status k3s
```
Install Worker
Grab token from the master node to be able to add worked nodes to it

```bash
sudo cat /var/lib/rancher/k3s/server/node-token
```
Go to the worker node and Install k3s on the worker node and add it to our cluster

```bash
sudo hostname worker
bash
sudo apt update
sudo apt -y upgrade

```

```bash
curl -sfL https://get.k3s.io | K3S_NODE_NAME=k3s-worker-01 K3S_URL=https://<MASTER-IP>:6443 K3S_TOKEN=<TOKEN> sh - 
```
You can verify if the k3s-agent on the worker nodes is running by

```bash
sudo systemctl status k3s-agent
```
To verify that our nodes have successfully been added to the cluster, run this command on the master

```bash
sudo kubectl get nodes -o wide
```

Check the resource usage with the following command before deployment 

```bash
top
```
| Node          | CPU           | Memory   |
| ------------- | ------------- | -------- |
| t2.micro Master        | 3.4           | 641.8    |
| t2.micro Worker        | 0.7           | 219.3    |


Setup NGINX Ingress Controller

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.1.2/deploy/static/provider/cloud/deploy.yaml
```

Wait for the ingress pods to come up and running

```bash
kubectl get pods --namespace=ingress-nginx
```

Check the resource usage with the following command after deployment 

```bash
top
```
| Node          | CPU           | Memory   |
| ------------- | ------------- | -------- |
| t2.micro Master        | 5.7           | 692.3    |
| t2.micro Worker        | 1.3           | 305.9    |


## Uninstalling K3s

To uninstall K3s from a server node, run

```bash
/usr/local/bin/k3s-uninstall.sh
```

To uninstall K3s from an agent node, run

```bash
/usr/local/bin/k3s-agent-uninstall.sh
```