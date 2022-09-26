// multistage
pipeline {
    agent any

        stages {
            stage('Source') {
                steps {
                    git url: 'https://github.com/Bangaruyogi77/dockerjenkins-demo.git'
                }
            }
            stage('Build Docker Image') {  
                steps{                     
                   bat 'docker-compose up'   
                    }
                }
            }
}
