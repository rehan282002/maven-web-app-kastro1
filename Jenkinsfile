pipeline {
    agent { label 'slave' }

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
    }
}
