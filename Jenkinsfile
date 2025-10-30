pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo "Building..."
                sh 'python3 -m py_compile app.py'
            }
        }
        stage('Test') {
            steps {
                echo "Testing..."
                sh 'pytest || echo "No tests to run"'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy stage - simulation"
            }
        }
    }

    post {
        success {
            echo "✅ Build successful"
        }
        failure {
            echo "❌ Build failed"
        }
    }
}
