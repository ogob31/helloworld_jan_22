pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }

        stage('Build') {
            steps {
                echo 'Running build stage...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
pipeline {
    agent any

    tools {
        maven 'Maven 3.8.5'  // 👈 Make sure this matches the name in Jenkins Global Tool Configuration
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting Build...'
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting Deploy...'
                sleep 10
                echo 'Deploy step complete'
            }
        }

        stage('Docker') {
            steps {
                echo 'Building Docker image...'
                // You can add: sh 'docker build -t your-image-name .'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully 🎉'
        }
        failure {
            echo 'Pipeline failed ❌'
        }
    }
}
