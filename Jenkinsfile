pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'ls -l'  // Check the files present in the workspace
                    sh 'g++ -o PES2UG22CS491 main/hello.cpp'  // Compile hello.cpp from the main directory
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './PES2UG22CS491' 
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
