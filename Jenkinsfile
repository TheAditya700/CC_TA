pipeline {
    agent any
    stages {        
        stage('Build') {
            steps {
                build 'PES1UG22AM013-1'
                sh 'g++ pipeline_test.cpp -o output'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
