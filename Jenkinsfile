pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub repo
                git url: 'https://github.com/LaveezaBukhari/ci-cd-project.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your actual build commands here
                // Example for Node.js:
                // sh 'npm install'
                // sh 'npm run build'

                // Example for Java (Maven):
                // sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deployment commands here
                // Example: copy files or restart service
                // sh 'cp -r * /var/www/html/'
                // sh 'sudo systemctl restart myapp'
            }
        }
    }
}
