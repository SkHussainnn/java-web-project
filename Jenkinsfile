pipeline {
    agent any

    tools {
        maven 'maven3.9'
    }

    stages {
        stage("checkout code") {
            steps {
                script {
                    echo "checkout code started"
                    git branch: 'main', url: 'https://github.com/SkHussainnn/java-web-project.git'
                    echo "checkout completed"
                }
            }
        }

        stage("Build Code") {
            steps {
                echo "Build Code started"
                sh 'mvn clean package'
                echo "Build Code completed"
            }
        }

        stage("Deployment") {
            steps {
                script {
                    echo "Deployment started"
                    deploy adapters: [tomcat9(url: 'http://18.142.254.53:8080/', credentialsId: 'tomcred')], war: 'target/*.war'
                    echo "Deployment completed"
                }
            }
        }
    }
}
