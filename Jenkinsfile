pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                
                sh 'g++ -o output_file main.cpp'
            }
            post {
                
                failure {
                    echo 'Build stage failed: pipeline failed'
                    currentBuild.result = 'FAILED'
                }
            }
        }
        stage('Test') {
            steps {
              
                sh './output_file'
            }
            post {
               
                failure {
                    echo 'Test stage failed: pipeline failed'
                    currentBuild.result = 'FAILED'
                }
            }
        }
        stage('Deploy') {
            steps {
                 echo 'deploy'
            }
            post {
               
                failure {
                    echo 'Deploy stage failed: pipeline failed'
                    currentBuild.result = 'FAILED'
                }
            }
        }
    }
}
