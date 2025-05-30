pipeline {
    agent any

    tools {
        maven 'MAVEN'   
    }

    triggers {
        githubPush()
    }

    environment {
        MAVEN_HOME = tool 'maven'
        PATH = "${MAVEN_HOME}/bin:${env.PATH}"
    }

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

        stage('Deploy') {
            steps {
                sh 'cp target/maven-web-app.war /opt/tomcat9/webapps/'
            }
        }
    }
}
