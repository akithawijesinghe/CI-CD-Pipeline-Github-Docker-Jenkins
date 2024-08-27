pipeline {
    agent any 
    
    stages { 
        stage('SCM Checkout') {
            steps {
                retry(3) {
                    git branch: 'main', url: 'https://github.com/akithawijesinghe/CI-CD-Pipeline-Github-Docker-Jenkins'
                }
            }
        }
        stage('Build Docker Image') {
            steps {  
                bat 'docker build -t akithawj/cicd-node-jen:%BUILD_NUMBER% .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'dockerhub-pass', variable: 'dockerpass')]) {
                    
                    bat 'docker login -u akithawj -p ${dockerpass}'
                    
                }
            }
        }
        stage('Push Image') {
            steps {
                bat 'docker push akithawj/cicd-node-jen:%BUILD_NUMBER%'
            }
        }
    }
    post {
        always {
            bat 'docker logout'
        }
    }
}
