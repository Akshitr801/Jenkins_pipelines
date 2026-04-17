pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Verify Files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Deploy to Server') {
            steps {
                echo 'Deploying static website...'
                sh '''
                    sudo cp -r * /var/www/html/
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment successful ✅'
        }
        failure {
            echo 'Deployment failed ❌'
        }
    }
}
