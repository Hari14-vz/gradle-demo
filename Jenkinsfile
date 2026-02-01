pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm 
            }
        }
        stage('Build & Test') {
            steps {
                sh 'chmod +x gradlew'
                sh './gradlew clean test assemble' 
            }
        }
        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube')
                {
                    sh './gradlew sonar'
                }
            }
        }
    }
}
