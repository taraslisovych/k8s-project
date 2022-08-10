pipeline {
    agent any

    stages {
        stage('Checkour sources from Git') {
          steps {
            git url: 'https://github.com/taraslisovych/k8s-project.git', branch: "main"
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
            sshagent(['build_server']) {
              //sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 cd ./docker'
              sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 docker build -t freezz187/k8s-httpd-php ./docker'
              sh 'ssh -o StrictHostKeyChecking=no ubuntu@34.249.104.69 docker images'

            }
          }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
