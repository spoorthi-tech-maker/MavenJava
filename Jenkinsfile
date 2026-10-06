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

    post {
        success {
            emailext(
                subject: "Jenkins Build Successful - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Jenkins build ${env.BUILD_NUMBER} completed successfully.",
                to: "spoorthi22107@gmail.com"
            )
        }

        failure {
            emailext(
                subject: "Jenkins Build Failed - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Jenkins build ${env.BUILD_NUMBER} failed. Please check the Jenkins console output.",
                to: "spoorthi22107@gmail.com"
            )
        }
    }
}
