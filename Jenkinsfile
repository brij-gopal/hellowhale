pipeline {
  agent any 
   stages {
    stage('Checkout Source') {
      steps {
        git url:'https://github.com/rushabhmahale/hellowhale.git', branch:'master'
      }
    }
    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: 'hellodocker.yml', kubeconfigId: "mykubeconfig")
        }
      }
    }
  }
}
