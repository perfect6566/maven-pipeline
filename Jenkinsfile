pipeline {
    agent any

    tools {
        maven 'mvn-3.5.4'
        jdk 'jdk-10.0.2'
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