pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                build 'PES2UG21CS066-1'
                sh 'g++ main.cpp -o output'
            }
          
        }
        stage('Test') {
            steps {
                
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
               sh 'g++ main.cpp -o ou
            }
            }
    }

        post{
            failure{
                error 'pipeline failed'
            }
        }
}

        
        

