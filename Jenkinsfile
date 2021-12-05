pipeline {

    agent any

     stages {
        stage('checkout') {
            steps {

                git 'https://github.com/kuslapur/50projects.git'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build . -t develop'
            }
        }
    }
}
