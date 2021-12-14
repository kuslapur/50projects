pipeline {

    agent any

     stages {
        stage('checkout') {
            steps {

                git branch: 'good-cheap-fast', url: 'https://github.com/kuslapur/50projects.git'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build . -t develop'
            }
        }

        stage('run image') {
            steps {
                sh 'docker run -d -p 80:80 develop'
            }
        }
    }
}
