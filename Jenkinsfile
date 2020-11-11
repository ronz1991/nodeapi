#!groovy

kubeconfigfile = """
apiVersion: v1
clusters:
- cluster:
    certificate-authority: /root/.minikube/ca.crt
    server: https://x.x.x.x:8443
  name: minikube
contexts:
- context:
    cluster: minikube
    user: minikube
  name: minikube
current-context: minikube
kind: Config
preferences: {}
users:
- name: minikube
  user:
    client-certificate: /root/.minikube/profiles/minikube/client.crt
    client-key: /root/.minikube/profiles/minikube/client.key
"""
node(){
      # if configured in scm plugin
      checkout scm
      
      #if not configured scm plugin
      sh('git clone http://github.com/ronz1991/nodeapi.git')
      
      writefile files 'config',text:configfile
      
      dir('nodeapi')
      {
          sh('cat' README.md')
          sh('kubectl get --configfile=$(PWD)/config')
      }
 }
