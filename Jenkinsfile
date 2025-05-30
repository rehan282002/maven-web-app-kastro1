pipeline {
    agent any

    tools {
        maven 'Maven' // Jenkins me configured Maven name
    }

    triggers {
        githubPush()
    }

    environment {
        MAVEN_HOME = tool 'Maven'
        PATH = "${MAVEN_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/rehan282002/insureme.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Deploy') {
            steps {
                // Old process kill (agar pehle se run ho raha ho)
                sh "pkill -f 'insure-me-1.0.jar' || true"

                // Run new JAR in background
                sh 'nohup java -jar target/insure-me-1.0.jar > app.log 2>&1 &'
            }
        }
    }
}
