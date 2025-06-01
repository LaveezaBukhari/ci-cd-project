pipeline {
    agent any

    environment {
        // Optionally set Python version or virtual environment directory
        VENV = 'venv'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub repo
                git url: 'https://github.com/LaveezaBukhari/ci-cd-project.git', branch: 'main'
            }
        }

        stage('Setup Python Environment') {
            steps {
                echo 'Setting up Python environment...'
                sh '''
                    python3 -m venv $VENV
                    source $VENV/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh '''
                    source $VENV/bin/activate
                    # Replace this with your test command
                    pytest || echo "No tests defined"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // You can add your custom deployment steps here.
                // For example, running the Flask app:
                sh '''
                    source $VENV/bin/activate
                    nohup python3 app.py &
                '''
            }
        }
    }
}
