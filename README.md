# MICROK8S

## snap
```
snap install microk8s --classic --channel=latest/stable

snap refresh microk8s --classic --channel=latest/stable

snap install microceph # Instalar Ceph

snap alias microk8s.kubectl k # Atajo rápido kubectl

sudo snap alias microk8s.helm h # Atajo rápido a helm 

sudo snap aliases

sudo snap unalias k

sudo snap unalias h
```

## iptables
```
apt install ufw htop vim net-tools iputils-ping

ufw default allow routed

iptables -P FORWARD ACCEPT
```

## microk8s 
```
microk8s start 

microk8s status

microk8s stop 

microk8s.inspect
```

## microk8s ha-cluster, add, list y remove
```
microk8s enable ha-cluster 

microk8s add-node

microk8s kubectl get nodes

microk8s remove-node bokeron5
```

## microk8s dashboard
```
microk8s enable dashboard 

microk8s kubectl describe secret -n kube-system microk8s-dashboard-token 

microk8s kubectl create token default  

microk8s kubectl port-forward -n kube-system service/kubernetes-dashboard 10443:443 --address='0.0.0.0' 

microk8s kubectl get po -A
```

## ceph install
```
microk8s enable rook-ceph

microk8s connect-external-ceph # Automático

microk8s helm repo add rook-release https://charts.rook.io/release # Manual

microk8s helm repo update # Manual

microceph cluster config list

microceph.ceph osd status
```

# kubectl metallb
```
microk8s enable metallb

microk8s enable ingress #Enter each IP address range delimited by comma: 192.168.1.110-192.168.1.114

```

# kubectl command
```
snap alias k = "microk8s kubectl"

k get pods -o wide

k get configmaps

k get services

k get ns # Mostrar namespaces

k get all # Todos los componentes

k get nodes # Listar los nodos

k get pod 

k get deploy 

k get replicaset

k top pod

k top nodes

k describe pod chatpad

k describe deploy

k describe service

k get pod -w
```

# chatpad

```
k get deployments

k scale --replicas=3 deployment/chatpad-deployment

k logs chatpad-6c97cbdf64-4nxjq # log del contenedor

k exec chatpad-6c97cbdf64-4nxjq -ti /bin/sh

k port-forward --address 0.0.0.0 chatpad-6c97cbdf64-4nxjq/chatpad 8080:80
```

