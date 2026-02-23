pipeline {
  agent any

  tools {

  maven Maven3

  }
  environment {
    PATH = "C:\\Program Files\\Docker\\Docker\\resources\\bin;${env.PATH}"
  }
 Stages{
    stage('check'){
        steps {
        git 'https://github.com/ADirin/TravelCal.git'
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
 }
}