pipeline {
    agent any

    stages {
        stage('Checkour sources from Git') {
          steps {
            git url: 'git@github.com/taraslisovych/k8s-project.git',
              branch: 'main'
            //sshagent(['build_server']) {

              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 mkdir ./docker'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 cd ./docker'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 touch ./docker/test1'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 git init'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 git remote add origin https://github.com/taraslisovych/k8s-project.git'
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 git pull'
            //}
          }
        }
        stage('Copy Docker image sources to the Build server') {
          steps {
            sshagent(['build_server']) {
              sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 cd ./docker'
              sh 'scp -o StrictHostKeyChecking=no ./docker/* ubuntu@34.249.104.69:/home/ubuntu/docker'
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
