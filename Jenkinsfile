pipeline {
    agent any

    stages {
        stage('fetch_code') {
            steps {
                git branch: 'expanding-cards', url: 'https://github.com/kuslapur/50projects.git'
            }
        }
        stage('Build') {
            steps {
               sh 'docker build . -t develop'    
            }
        }
        stage('deploy'){
            steps {
               sh 'docker run -d -p 80:80 develop'
            }
        }
	stage ('upload'){
	    steps {

       nexusArtifactUploader credentialsId: '27f206c7-dae0-4bbb-91a8-19ae06ccdfb6', groupId: 'nexus', nexusUrl: 'http://3.23.17.66:8081/repository/maven-releases/', nexusVersion: 'nexus2', protocol: 'http', repository: 'http://3.23.17.66:8081/repository/maven-releases/', version: '1.1'
        }
      }
      
      }
}
