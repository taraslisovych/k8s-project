pipeline {
    agent any

    stages {
        stage('Checkour sources from Git') {
          steps {
            sshagent(['build_server']) {
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 mkdir ./docker'
              sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 cd ./docker'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 touch ./docker/test1'
              script {
                git branch: "main",
                url: "https://github.com/taraslisovych/k8s-project.git"
              }
            }
          }
        }
        stage('Build and push Docker image') {
          steps {
              echo 'Hello World'
          }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
