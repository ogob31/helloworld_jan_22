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
        maven 'M2_HOME'  // Change 'M2_HOME' if your Maven tool in Jenkins has a different name
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
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
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
                sleep 5
            }
        }

        stage('Docker') {
            steps {
                echo 'Docker image stage (placeholder)'
                // Example: sh 'docker build -t my-image .'
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
