pipeline{
    agent any
    stages{
        stage('Build App'){
            steps{
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/hereazim/projCert.git']])
            
            }
        }
        stage('Build Docker'){
            steps{
                script{
                    bat 'docker build -t kaazim/phpapp .'
                    
                }
            }
        }
        stage('Push Docker'){
            steps{
                script{
                    bat 'docker login -u kaazim -p Azimka@01#'
                    bat 'docker push kaazim/phpapp'
                }
            }
        }
        
    }
}
