pipeline {
    agent any

    environment {
        WAR = "target/maven-web-app.war"
        DEST = "/opt/tomcat9/webapps"
    }

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
                sh "sudo cp ${WAR} ${DEST}/"
            }
        }
    }
}
