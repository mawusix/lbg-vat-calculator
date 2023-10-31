pipeline {
  agent any

  stages {
    stage('Checkout') {
        steps {
          // Get some code from a GitHub repository.
          git branch: 'main', url: 'https://github.com/mawusix/lbg-vat-calculator.git'
        }
    }
    stage('SonarQube Analysis') {
      environment {
        scannerHome = tool 'sonarqube'
      }
        steps {
            withSonarQubeEnv('sonar-qube') {        
              sh "${scannerHome}/bin/sonar-scanner"
            }   
        }
    }
  }
}