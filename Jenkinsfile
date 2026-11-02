pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/AsaD-04/capstone-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t capstone-web .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop website || true
                docker rm website || true
                docker run -d --name website -p 80:80 capstone-web
                '''
            }
        }
    }
}
