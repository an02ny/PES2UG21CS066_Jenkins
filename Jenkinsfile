pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Compile the .cpp file using a shell script
                sh 'g++ -o output_file main.cpp'
            }
            post {
                // Display 'pipeline failed' if the Build stage fails
                failure {
                    echo 'Build stage failed: pipeline failed'
                    currentBuild.result = 'FAILED'
                }
            }
        }
        stage('Test') {
            steps {
                // Print output of .cpp file using a shell script
                sh './output_file'
            }
            post {
                // Display 'pipeline failed' if the Test stage fails
                failure {
                    echo 'Test stage failed: pipeline failed'
                    currentBuild.result = 'FAILED'
                }
            }
        }
        stage('Deploy') {
            steps {
                // Perform deployment steps if needed
            }
            post {
                // Display 'pipeline failed' if the Deploy stage fails
                failure {
                    echo 'Deploy stage failed: pipeline failed'
                    currentBuild.result = 'FAILED'
                }
            }
        }
    }
}
