pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/YashVMishra/Text-to-Emoji-E-D'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t text-to-emoji-app .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker stop text-to-emoji-app || true'
                    sh 'docker rm text-to-emoji-app || true'
                    sh 'docker run -d -p 8080:80 --name text-to-emoji-app text-to-emoji-app'
                }
            }
        }
    }
}

