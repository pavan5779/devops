pipeline {
    agent any
       
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn compile' 
            }
        }
        // Testing stage runs unit tests
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'mvn clean package'
            }
        }
    }
    post {
        failure {
            echo 'One or more stages failed, but pipeline will continue...'
            // You can add additional actions here, such as sending notifications or performing cleanup tasks.
        }
    }
}
