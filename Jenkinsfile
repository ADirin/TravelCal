pipeline {
  agent any

  tools {

    maven 'Maven3'

  }
  environment {
    PATH = "C:\\Program Files\\Docker\\Docker\\resources\\bin;${env.PATH}"
  }
 stages{
    stage('check'){
        steps {
            git url: 'https://github.com/ADirin/TravelCal.git'
       }
    }

    stage('build job: '){
        steps {
          bat  'mvn clean install'
        }
    }
    stage('test'){
        steps {
          bat 'mvn test'
        }
    }
    stage('Report'){
        steps {
             bat 'mvn jacoco:report'
        }
    }

    stage('Publish Test Results') {
           steps {
              junit '**/target/surefire-reports/*.xml'
           }
    }
    stage('Publish Coverage Report') {
            steps {
                jacoco()
            }
    }

 }
}