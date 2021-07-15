#!/usr/bin/env groovy

pipeline {
    agent {
    label "awsagent"
    }

    tools {
        maven 'mvn-3.5.4'
        jdk 'jdk-8u181'
    }

    stages {
        stage('Build') {
            steps {
                sh "printenv"
                sh "mvn clean test package spring-boot:repackage"

            }
        }

    }
    post {
        always{
//            junit 'target/surefire-reports/**/*.xml'
            junit(testResults: '**/target/surefire-reports/**/*.xml')
//             jacoco(
//                     execPattern: 'target/**/*.exec',
//                     classPattern: 'target/classes',
//                     sourcePattern: 'src/main/java',
//                     exclusionPattern: 'src/test*',
//                     buildOverBuild: true,
//                     changeBuildStatus: true,
//                     deltaLineCoverage: '69',
//                     minimumLineCoverage:'0',
//                     maximumLineCoverage: '61'
//             )
            archiveArtifacts artifacts : 'target/**/*.jar',fingerprint:true

        }

    }
}
