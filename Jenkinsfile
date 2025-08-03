pipeline {
    agent any

    tools {
        maven 'M2_HOME' // Match this to your Jenkins global Maven tool name
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Build') {
            steps {
                echo 'Running build stage...'
                sh 'mvn clean install package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }

        stage('Docker') {
            steps {
                echo 'Docker image build step'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully.'
        }
        failure {
            echo '❌ Pipeline failed.'
        }
    }
}


