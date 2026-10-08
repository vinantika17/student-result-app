pipeline {

    agent any

    tools {
        maven 'maven'
        jdk 'java21'
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: 'target/student-result.war',
                                     fingerprint: true
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                echo 'Deploying student-result.war to Tomcat...'
            }
        }
    }
}
