pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Insert your build commands here, e.g., mvn clean install
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
