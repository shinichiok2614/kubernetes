https://www.youtube.com/watch?v=yOBeQNGX278&list=PLwJr0JSP7i8D-QS50lYsXpAg-jYoqxMVy&index=1&t=299s

# cài vagrant cho mac
brew tap hashicorp/tap
brew install hashicorp/tap/hashicorp-vagrant

#
kubectl version --short

kubectl cluster-info

kubectl get node

kubectl describe node/docker-desktop

# chế độ chạy được
chmod +x install-docker-kube.sh

master git:(main) ✗ vagrant up        

mkdir worker1
mkdir worker2
master git:(main) ✗ vagrant reload
worker1 git:(main) ✗ vagrant up
worker2 git:(main) ✗ vagrant up

ssh root@192.168.10.100
>yes
>123
[root@master ~]# docker version

ssh root@192.168.10.101
>yes
>123
[root@worker1 ~]# docker version

ssh root@192.168.10.102
>yes
>123
[root@worker2 ~]# docker version

# https://docs.tigera.io/calico/latest/getting-started/kubernetes/quickstart
[root@master ~]# kubeadm init --apiserver-advertise-address=192.168.10.100 --pod-network-cidr=192.168.0.0/16

# docker và podman
# https://blog.vietnamlab.vn/container-va-cac-cong-cu-quan-ly-container/
# high-level container management, high, low-level runtime
# https://www.cloudnativeviet.net/post/2020/12/25/container-runtime-detail-p1/
# runc
# https://www.cloudnativeviet.net/post/2020/12/25/container-runtime-detail-p2/
# docker: dockerd daemon (build image): (high-level) docker-containerd daemon (ctr), (low-level)docker-runc
# https://www.cloudnativeviet.net/post/2021/02/20/container-runtime-detail-p3/


TRANDUCTRINH
https://www.youtube.com/watch?v=TTNsHaOxU10&list=PLPA5WSROSsagXbBQTXmG9Rss-lhvAsID9&index=1
https://app.vagrantup.com/boxes/search
generic/ubuntu2004
Authentication Tokens
/.ssh/id_rsa.pub

Nana
https://www.youtube.com/watch?v=X48VuDVv0do 42.00
https://minikube.sigs.k8s.io/docs/start/

brew update
brew install hyperkit
brew install minikube
kubectl
minikube
minikube start --vm-driver=hyperkit
kubectl get nodes  //get status of nodes
minikube status
kubectl version

//kubectl CLI: for configuring the minikube cluster
//minikube CLI: for start up/deleting the cluster

kubectl get pod
kubectl create -h

//Pod is the smallest unit

//deployment - abstraction over Pods

kubectl create deployment nginx-depl --image=nginx
kubectl get deployment
kubectl get pod

//blueprint for creating Pods

kubectl get replicaset 

//replicaset is managing the replicas of a pod
kubectl edit deployment nginx-depl
    :q! không lưu và thoát
    :w lưu
    :q thoát
    - image: nginx:1.16
kubectl get deployment
kubectl get pod  //id pod thay đổi
kubectl logs nginx-depl-6bdcdf7f5-qtvtg  <-pod name
kubectl create deployment mongoj-depl --image=mongo
kubectl get pod
kubectl logs mongoj-depl-66c4dbd6f9-d9x94

kubectl describe pod mongoj-depl-66c4dbd6f9-d9x94

kubectl exec -it mongoj-depl-66c4dbd6f9-d9x94 -- bin/bash
# ls
# exit
kubectl get deployment
kubectl get pod
kubectl delete deployment mongoj-depl
kubectl get pod

kubectl delete deployment nginx-depl 
kubectl get pod
kubectl apply -f nginx-deployment.yaml
touch nginx-deployment.yaml
vim nginx-deployment.yaml
    replicas: 1
kubectl apply -f nginx-deployment.yaml
kubectl get pod
kubectl get deployment
vim nginx-deployment.yaml
    replicas: 2
kubectl apply -f nginx-deployment.yaml

// deployment manages a rs
// replicaSet (rs) manages a pod
// pod is an abstraction of container

1:11:08