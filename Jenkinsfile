pipeline {
    agent any

    tools {
        maven 'mvn-3.5.4'
    }

    environment {
        PATH = "invalid path"
    }

    stages {
        stage('Build') {
            steps {
               sh "printenv"
               sh "mvn clean package spring-boot:repackage"
            }
        }
    }
}