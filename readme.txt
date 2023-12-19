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
