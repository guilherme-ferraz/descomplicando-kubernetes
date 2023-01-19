Instalar kind

curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.17.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind


Instalar kubectl

curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

chmod +x ./kubectl

sudo mv ./kubectl /usr/local/bin/kubectl

kubectl version --client


Criar cluster
kind create cluster --config meu-primeiro-cluster.yaml

Criar pod
kubectl create -f meu-primeiro-pod.yaml

Expor o pod
kubectl expose pod meu-nginx

kubectl run meu-nginx --image nginx --dry-run=client --port=80 -o yaml > pod-template.yaml


