pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/Sowju27/PES2UG22CS572_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ mai/hello.cpp -o main/output'
            }
        }

        stage('Test') {
            steps {
                sh './mai/output'
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
