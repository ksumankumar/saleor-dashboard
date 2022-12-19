pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/ksumankumar/saleor-dashboard.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t 8520005318/saleor-dashboard:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push 8520005318/saleor-dashboard:DEV'
            }
        }
    }
}
