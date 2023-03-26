pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar' //so that they can be downloaded later
        //first commit      
            }
        }
      stage('Unit Test') {
            steps {
              sh "mvn test"
            }
  
      }
      stage('Docker build and push') {
            steps {
              sh "printenv"
              sh 'docker build siddharth67/numeric-app .'
              sh 'docker push siddharth67/numeric-app'
            }
        }
    
    }
}
