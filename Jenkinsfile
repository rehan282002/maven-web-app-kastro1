pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/rehan282002/maven-web-app-kastro1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh 'sudo cp target/*.war /opt/tomcat9/webapps/'
            }
        }
    }
}
