pipeline {
    agent any
        
    tools {
        maven 'maven3.9'
    }

    stages {
        stage("checkout code") {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/SkHussainnn/java-web-project.git'
                }
            }
            stage("Build Code"){
                steps{
                    sh 'mvn clean package'
                }
            }
        }
    }
}

