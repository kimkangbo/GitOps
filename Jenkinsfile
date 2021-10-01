pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // Git-URL will replace by sed command before RUN
        git url: 'git@github.com:kimkangbo/GitOps.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}
