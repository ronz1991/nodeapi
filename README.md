# centos 7.6.18(minimal)
Hardware: 8GBRAM-4CPU-50GB(VM)

Software: Dockerengine,minikube,conntrack(for minikube)

# nodeapi running on docker
I want to be sure that the nodejs-api work,so i build it on a docker

1. create a package.json

2. create a server.js

3. create a Dockerfile

4. build the docker

5. run the docker 
# nodeapi running on kubernetes(minikube)
1.minikube install

2.curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

3.sudo install minikube-linux-amd64 /usr/local/bin/minikube

4.yum install conntrack(necessary for minikube)

5.minikube start --driver=none

6.export PATH=/usr/local/bin:$PATH

7.export KUBECONFIG=/usr/local/bin/kubectl

# kubernetes deployment
1.create a namespace : 'kubectl create namespace api-servers'

2.create a yaml with all the deployment config : 'touch deployment.yaml'

# Jenkinsfile
1.I assumed that your aren't running on the master and you have a 'slave' for Jenkins builds.

2.I assumed that you have a secret for project and builds for connecting to the kubernetes throw the plugin.


