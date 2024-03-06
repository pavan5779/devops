pipeline {
    agent any
       
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn test' 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'mvn deploy'
            }
        }
    }
    post {
        failure {
            echo 'One or more stages failed, but pipeline will continue...'
        }
    }
}
