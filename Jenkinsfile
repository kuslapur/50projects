pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                git branch: 'feedback-ui-design', url: 'https://github.com/kuslapur/50projects.git'
            }
        }
        stage('build app') {
          steps {
                sh 'docker build . -t develop'
          }
        }
        stage('deploy app') {
            steps {
                sh 'docker run -d -p 80:80 develop'
            }
        }
    }
}
