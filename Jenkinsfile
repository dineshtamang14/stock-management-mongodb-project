pipeline {
    agent {
        docker {
            image 'node:lts-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t dineshtamang14/stock:v1'
            }
        }
        stage('Deliver') { 
            steps {
                sh 'docker run -itd -p 3000:3000 --name test dineshtamang14/stock:v1' 
            }
        }
    }
}
