brew install kubectl
kubectl version --client
// minikube is a tool - run k8s locally, runs a single-node k8s cluster
brew install minikube
minikube start --driver=virtualbox    
minikube status
minikube ip
ssh docker@192.168.64.3      #nếu sử dụng driver=docker thì dùng minikube ssh vì ssh docker k dùng dc
    docker      #username
    tcuser      #pass
minikube stop
minikube delete
minikube version

https://www.youtube.com/watch?v=d6WC5n9G_sM&t=1909s
https://youtu.be/d6WC5n9G_sM?si=pJp5pqE34EFHAWxw&t=1941

minikube ssh -n minikube
    docker ps
    kubectl
    exit
kubectl cluster-info
    Kubernetes control plane is running at https://192.168.64.4:8443
    CoreDNS is running at https://192.168.64.4:8443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
kubectl get nodes
kubectl get pods
kubectl get namespace
kubectl get pods --namespace=kube-system
kubectl run nginx --image=nginx
    pod/nginx created
kubectl get pods
kubectl describe pod nginx
    Name:             nginx
    Namespace:        default
    Priority:         0
    Service Account:  default
    Node:             minikube/192.168.64.4
    IP:               10.244.0.3
    Image:          nginx
minikube ssh -n minikube
    docker ps | grep nginx
    docker exec -it c6f5571a08ac sh
        hostname 
            nginx
        hostname -i
            10.244.0.3
        curl 10.244.0.3
    exit
    exit
kubectl get pods -o wide    # output, wide: mở rộng
    nginx   1/1     Running   0          68m   10.244.0.3
curl 10.244.0.3
    xxx

https://youtu.be/d6WC5n9G_sM?si=5WFkb_IyObiYsdqE&t=3104