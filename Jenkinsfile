pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:/usr/local/bin:/Applications/Docker.app/Contents/Resources/bin:${env.PATH}"
    }

    stages {
        stage('Check Docker') {
            steps {
                sh 'which docker'
                sh 'docker --version'
                sh 'docker info'
            }
        }

        stage('Build') {
            steps {
                sh 'docker pull maven:3.10.0-eclipse-temurin-21-alpine'
            }
        }
    }
}