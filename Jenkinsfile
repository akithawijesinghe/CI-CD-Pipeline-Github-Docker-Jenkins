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
                script {
                    bat 'docker build -t akithawj/cicd-node-jen:%BUILD_NUMBER% .'
                }
            }
        }
        stage('Login to Docker Hub') {
            steps {
                script {
                    withCredentials([string(credentialsId: 'docker-pass', variable: 'dockerpass-vari')]) {
                        bat 'docker login -u akithawj -p %dockerpass-vari%'
                    }
                }
            }
        }
        stage('Push Image') {
            steps {
                script {
                    bat 'docker push akithawj/cicd-node-jen:%BUILD_NUMBER%'
                }
            }
        }
    }
    post {
        always {
            script {
                bat 'docker logout'
            }
        }
    }
}
