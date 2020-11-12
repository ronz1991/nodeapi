#!groovy

kubeconfigfile = """
apiVersion: v1
clusters:
- cluster:
    certificate-authority: ./ca.crt
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
    client-certificate: ./client.crt
    client-key: ./client.key
"""
node() {
    
        // cleanning workspace
        sh('rm * -rf')
        
      // if configured in scm plugin
      // checkout scm

      // if not configured scm plugin
      
      sh('git clone http://github.com/ronz1991/nodeapi.git')
      // 
      writeFile file: 'config', text: kubeconfigfile
      writeFile file: 'client.crt', text: clientcertfile
      writeFile file: 'client.key', text: clientkeyfile
      writeFile file: 'ca.crt', text: cacertfile
      // writefile files 'config', text: configfile
      
      dir('nodeapi')
      {
          sh('cat README.md')
          sh('kubectl --kubeconfig=../config get all')
          sh('kubectl --kubeconfig=../config apply -f deployment.yaml')
      }
 }
