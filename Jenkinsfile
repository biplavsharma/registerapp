pipeline {
  agent { label 'Jenkins_slave'}
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
    stage("Cleanup Workspace"){
       steps {
         cleanWs ()
      }
     }
    stage("Checkout from SCM"){
      steps {
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/biplavsharma/registerapp'
      }
     }
    stage("Build Application"){
      steps {
        sh "mvn clean package"
      }
     }
    stage("Test Applicaiton"){
      steps {
        sh "mvn test"
      }
     }
  }
}
