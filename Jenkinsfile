pipeline {
    agent {label 'node'}
    triggers { pollSCM('* * * * *') }
    stages {
        stage('git') {
            steps {
                git branch: 'main', url: 'https://github.com/gopivurata/saleor-dashboard.git'
            }
        }
        stage('docker') {
            steps {
                sh '''docker info
                  docker image build -t gopivurata/salore-dashboard:DEV .
                  docker image push gopivurata/salore-dashboard:DEV'''
            }
        }
    }
}