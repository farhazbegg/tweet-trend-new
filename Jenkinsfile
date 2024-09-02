pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Insert your build commands here 123, e.g., mvn clean install
            }
        }

    stage('SonarQube analysis') {
    environment {
      scannerHome = tool 'valaxy-sonar-scanner'
    }
    steps{
    withSonarQubeEnv('valaxy-sonarqube-server') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
  }
    
        stage('Test') {
            steps {
                echo 'Testing...'
                // Insert your test commands here, e.g., mvn test
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Insert your deploy commands here, e.g., scp target/*.jar user@server:/deploy
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            // Add any cleanup commands here
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
