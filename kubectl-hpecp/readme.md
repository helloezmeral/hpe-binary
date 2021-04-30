# install
```bash
wget https://bluedata-releases.s3.amazonaws.com/kubectl-epic/3.4/14/linux/kubectl-hpecp.star
tar xf kubectl-hpecp.star
# move the file to the path
kubectl plugin list
wget https://storage.googleapis.com/kubernetes-release/release/v1.18.6/bin/linux/amd64/kubectl
# move the file to the path
```
# usage
```bash
# install the kubectl
curl -LO "<https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl>"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
# or
snap install kubectl --classic
# or
wget https://storage.googleapis.com/kubernetes-release/release/v1.18.6/bin/linux/amd64/kubectl
chmod +x kubectl


# install HPE-kubectl
kubectl plugin list
wget https://bluedata-releases.s3.amazonaws.com/kubectl-epic/3.4/14/linux/kubectl-hpecp.star
tar xf kubectl-hpecp.star

# move the file to PATH
sudo mv ./kubectl-hpecp /usr/local/bin
kubectl plugin list
kubectl hpecp -h
kubectl hpecp version	
kubectl hpecp version --output=yaml

# kubeconfig
kubectl hpecp refresh 172.16.10.41 --insecure --hpecp-user=your_username --hpecp-pass=your-pass
kubectl hpecp refresh ez53-gateway.hpeilab.com --insecure --hpecp-user=your_username --hpecp-pass=your-pass
kubectl hpecp refresh ez53-gateway.hpeilab.com --insecure

export KUBECONFIG="/home/hpeadmin/.kube/.hpecp/ez53-gateway.hpeilab.com/config"
KUBECONFIG="/home/hpeadmin/.kube/.hpecp/ez53-gateway.hpeilab.com/config:/home/hpeadmin/.kube/config" kubectl config view
```

# Alternative using kubeconfig file
- This is a temperary method, the key will expire
```
hpeadmin@awb51:~/myAWB/app01/deliverables$ nano kubeconfig
hpeadmin@awb51:~/myAWB/app01/deliverables$ export KUBECONFIG=./kubeconfig 
hpeadmin@awb51:~/myAWB/app01/deliverables$ kubectl get pods

save the kubeconfig file
export=KUBECONFIG="kubeconfig"
kubectl get pods
```

# Kubedirector
```
# these are running application
kubectl get KubeDirectorCluster
kubectl delete  KubeDirectorCluster codeserver

```
