pipeline {

    agent any

     stages {
        stage('checkout') {
            steps {

                git branch: 'good-cheap-fast', url: 'https://github.com/kuslapur/50projects.git'a
            }
        }
        stage('Build') {
            steps {
                sh 'docker build . -t develop'
            }
        }
    }
}
