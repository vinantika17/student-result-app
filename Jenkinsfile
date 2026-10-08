pipeline {

    agent any

    tools {
        maven 'Maven3'
        jdk 'Java21'
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
pipeline {

    agent any

    tools {
        maven 'Maven3'
        jdk 'Java17'
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
}}
