pipeline {
      agent any

      stages {
         stage('Build') {
            steps {
               sh './gradlew clean compileJava'
               sh './gradlew clean assemble'
            }
         }
         stage('Deploy'){
            steps{
                sh 'cf push account-service -p ./build/libs/account-service-0.0.1-SNAPSHOT.jar'
            }
         }
      }
  }