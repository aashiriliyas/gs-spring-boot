pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/aashirilyas/gs-spring-boot.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh './mvnw clean package' // If using Maven Wrapper
                // or
                // sh 'mvn clean package' // If Maven is installed
            }
        }
        stage('Test') {
            steps {
                sh './mvnw test' // If using Maven Wrapper
                // or
                // sh 'mvn test' // If Maven is installed
            }
        }
        stage('Deploy') {
            steps {
                // Add your deployment steps here
                echo 'Deploying application...'
                // e.g., sh 'deploy-script.sh'
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
