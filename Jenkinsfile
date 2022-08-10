pipeline {
    agent any

    stages {
        stage('Checkour sources from Git') {
          steps {
            sshagent(['build_server']) {
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 mkdir ./docker'
              sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 cd ./docker'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 touch ./docker/test1'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 git init'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 git remote add origin https://github.com/taraslisovych/k8s-project.git'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 git pull'
              git 'https://github.com/taraslisovych/k8s-project.git'
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
