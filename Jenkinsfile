
pipeline {
    agent {
        docker {
            image 'maven:3.9.9-eclipse-temurin-21-alpine'
            args '-e HOME=/tmp -e MAVEN_CONFIG=/tmp/.m2'
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
                sh 'mvn -Dmaven.repo.local=/tmp/.m2/repository clean package'
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
