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

   tools{

       maven 'M2_HOME'

   }
   stages {

       stage('Build') {

           steps {

               sh 'mvn clean'

               sh 'mvn install'

               sh 'mvn package'

           }

       }

       stage('Test') {

           steps {

               sh 'mvn test'

           }

       }

       stage('Deploy') {

           steps {

               echo 'Deploy Step'

               sleep 10

           }

       }

       stage('Docker') {

           steps {

               echo 'Image step'

           }
       }
   }
}
