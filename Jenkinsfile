pipeline {

    // Jenkins will run this on any available agent
    agent any

    stages {

        // -------------------------
        stage('Checkout Code') {
            steps {
                // Pull latest code from GitHub
                git branch: 'main', url: https://github.com/Akshitr801/Jenkins_pipelines.git'
            }
        }

        // -------------------------
        stage('Deploy to Server') {
            steps {
                sh '''
                    echo "Deploying website to Nginx..."

                    // Copy files to web server directory
                    sudo cp -r * /var/www/html/

                    // Restart nginx to reflect changes
                    sudo systemctl restart nginx
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment successful 🚀"
        }

        failure {
            echo "Deployment failed ❌"
        }
    }
}
