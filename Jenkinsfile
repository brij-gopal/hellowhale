pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/rushabhmahale/jenkwebui-deployment.git', branch:'master'
      }
    }
    stage('List pods') {
        withKubeConfig([credentialsId: 'mykubeconfig',
                    serverUrl: 'https://192.168.99.100:8443',
                    clusterName: 'minikube',
                    namespace: 'default'
                    ]) {
      sh 'kubectl get pods'
     }
   }
  }
}
