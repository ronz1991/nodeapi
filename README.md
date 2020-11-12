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
1. minikube install

2. curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

3. sudo install minikube-linux-amd64 /usr/local/bin/minikube

4. yum install conntrack(necessary for minikube)

5. minikube start --driver=none

6. export PATH=/usr/local/bin:$PATH

7. export KUBECONFIG=/usr/local/bin/kubectl

# kubernetes deployment
1. create a namespace : 'kubectl create namespace api-servers'

2. create a yaml with all the deployment config : 'touch deployment.yaml'

3. apply the deployment : 'kubectl apply -f deployment.yaml'

4. I assumed that you have an LoadBalancer otherwise you need to use 'NodePort' parameter in the 'Service' Kind deployment.

# Jenkins server(on docker)

1. Install the server : 'docker run -d -v jenkins_home:/var/jenkins_home --net=host -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts'

2. Copy the 'kubectl' : 'docker cp /usr/local/bin/kubectl dockername:/usr/local/bin/.'

3. Choose the default Plugins 

# Jenkinsfile
1. I assumed that you aren't running on the master and you have a 'slave' for Jenkins builds.

2. I assumed that you have a secret for project and builds for connecting to the kubernetes through the plugin.

3. I didnt use kubernetes plugin! 

4. Please add the parameters of the kubernetes cluster config.


