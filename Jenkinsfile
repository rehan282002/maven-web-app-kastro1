pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/rehan282002/maven-web-app-kastro1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo cp target/maven-web-app.war /opt/tomcat9/webapps/'
            }
        }
    }
}
