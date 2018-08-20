pipeline {
    agent {
        docker {
            image 'php:7.2-apache'
            args '-p 80:1234'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('build') {
            steps {
                sh 'php --version'
            }
        }
        stage('deliver') {
            steps {
                //sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                //sh './jenkins/scripts/kill.sh'
            }
        }
    }
}