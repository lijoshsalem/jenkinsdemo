pipeline {
    agent { docker { image 'maven:3.10.0-eclipse-temurin-21-alpine' } }

    environment {
        PATH = "/opt/homebrew/bin:/usr/local/bin:/Applications/Docker.app/Contents/Resources/bin:${env.PATH}"
    }

    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        }
    }
}