pipeline {
    agent any

    tools {
        maven 'MAVEN-HOME'
    }

    stages {
        stage('clean') {
            steps {
                bat 'mvn clean'
            }
        }

        stage('install') {
            steps {
                bat 'mvn install'
            }
        }

        stage('test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('package') {
            steps {
                bat 'mvn package'
            }
        }
    }
}
