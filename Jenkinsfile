pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-21-alpine'
        }
    }

    stages {
        stage('Check Java and Maven') {
            steps {
                sh 'java -version'
                sh 'mvn --version'
            }
        }

        stage('Build Spring Boot App') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo 'Spring Boot build successful!'
        }
        failure {
            echo 'Build failed. Check the console output.'
        }
    }
}