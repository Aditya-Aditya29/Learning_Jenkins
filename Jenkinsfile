pipeline {
    agent any


        tools{
        nodejs "NodeJS 16"
        }

        stages{
            stage("Clone Repository"){
                steps{
                    git 'https://github.com/Aditya-Aditya29/Learning_Jenkins.git'
                }
        }

        stage("Install Dependencies"){
                steps{
                    sh 'npm i'
                }
        }
        stage('Build Docker Image'){
                steps{
                    sh 'docker build -t learning-jenkins .'
                }
        }
        stage('Run Docker Container'){
                steps{
                    sh 'docker run -d -p 3000:3000 learning-jenkins'
                }
        }
    }

}