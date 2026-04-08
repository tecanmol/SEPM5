pipeline {
    agent any

    tools {
        maven 'Maven-3.9.0'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/tecanmol/SEPM5.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                bat 'copy target\\*.war C:\\Users\\pande\\Downloads\\apache-tomcat-10.1.54-windows-x64\\apache-tomcat-10.1.54\\webapps\\'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed. App deployed to Tomcat.'
        }
        failure {
            echo 'Pipeline failed. Check console output.'
        }
    }
}
