#!groovy

configfile = """
             
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
