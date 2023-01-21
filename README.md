# Prometheus
Monitor a Kubernetes Cluster with Prometheus and Grafana

Used Kind <3

kind create cluster --name monitoring --image kindest/node:v1.24 --config kind.yaml

test the cluster:

kubectl get nodes





manifests retreived from :
https://github.com/prometheus-operator/kube-prometheus.git

This is how I did it:
Used docker to get it - 

docker run -it -v ${PWD}:/work -w /work alpine sh (install git: apk add git)

Make sure you use the compatibility matrix provided. (only the latest revision history)

git clone --depth 1 https://github.com/prometheus-operator/kube-prometheus.git -b release-0.11 /tmp/

copy the goods (I only wanted the manifests folder this time, also the setup folder is inside the manifests dir):

cp -R /tmp/manifests .


Custom Resource Definitions:

kubectl create -f ./manifests/setup/

kubectl create -f ./manifests/

This step took a few minutes:

kubectl -n monitoring get pods (Wait for the running status of all pods, that worked best for me)






![Screenshot_20230121_182947](https://user-images.githubusercontent.com/8779526/213882008-432acd7b-4225-416e-bbb2-cc6291456638.png)


![Screenshot_20230121_183458](https://user-images.githubusercontent.com/8779526/213882010-cab44b57-d1e1-438e-ba10-fd848ed77863.png)


![Screenshot_20230121_183911](https://user-images.githubusercontent.com/8779526/213882159-7ec0982a-f426-459f-881d-5dfeb33b1833.png)









