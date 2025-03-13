pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    useRemoteConfigs: [[url: 'https://github.com/SUSHIL1102/PES1UG22CS636_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG22CS636_1'
                sh 'g++ main/new.cpp -o output'
            }
        }
       stage('Test') {
            steps {
                sh './wrong_output'  // This file does not exist!
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
