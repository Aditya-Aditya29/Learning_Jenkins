pipeline {
    agent any

    tools {
        nodejs "NodeJS 24"  // Make sure you've configured this name under Jenkins > Global Tool Configuration
    }

    stages {
        stage("Clone Repository") {
            steps {
                git branch: 'main', url: 'https://github.com/Aditya-Aditya29/Learning_Jenkins.git'
            }
        }

        stage("Install Dependencies") {
            steps {
                sh 'npm install'
            }
        }

        stage("Build Docker Image") {
            steps {
                sh 'docker build -t learning-jenkins .'
            }
        }

        stage("Run Docker Container") {
            steps {
                sh 'docker run -d -p 3000:3000 learning-jenkins'
            }
        }
    }
}
