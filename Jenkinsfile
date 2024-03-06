pipeline {
    agent any
       
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn compile' 
            }
        }
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
        }
    }
}
