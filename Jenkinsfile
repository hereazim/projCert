pipeline{
    agent any
    stages{
        stage('Build App'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/hereazim/projCert.git']])
                build 'Check-in'
            }
        }
        stage('Build Docker'){
            steps{
                script{
                    bat 'docker build -t kaazim/phpApp .'
                    
                }
            }
        }
        stage('Push Docker'){
            steps{
                script{
                    bat 'docker login -u kaazim -p Azimka@01#'
                    bat 'docker push kaazim/phpApp'
                }
            }
        }
        
    }
}
