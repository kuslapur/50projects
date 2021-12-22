pipeline {
    agent any

    stages {
        stage('fetch_code') {
            steps {
                git branch: 'auto-text-effect', url: 'https://github.com/kuslapur/50projects.git'
            }
        }
        stage('Build') {
            steps {
               sh 'docker build . -t develop'    
            }
        }
        stage('deploy'){
            steps {
               sh 'docker run -it -p 80:80 develop -d'
            }
        }
      
      }
}
