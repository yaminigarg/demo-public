pipeline {
  agent {
    kubernetes {
      label 'demo-app'  // all your pods will be named with this prefix, followed by a unique id
      idleMinutes 5  // how long the pod will live after no jobs have run on it
      yamlFile 'k8sdemo.yaml'  // path to the pod definition relative to the root of our project 
      defaultContainer 'jenkinsagent'  // define a default container if more than a few stages use it, will default to jnlp container
    }
  }
  stages {
    /*
    stage('Build') {
      steps {  // no container directive is needed as the maven container is the default
        sh 'npm --version'   
      }
    }
    */
    stage('Build Docker Image') {
      steps {
        container('jenkinsagent') {
          sh '''
          mkdir -p abc
          apt update
          apt install git
          git clone https://github.com/yaminigarg/demo-public.git
            '''
        }
      }
    }
  }
}
