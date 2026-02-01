pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm // Pulls from GitHub[span_2](end_span)[span_3](end_span)
            }
        }
        stage('Build & Test') {
            steps {
                sh './gradlew clean test' // Executes Gradle build[span_4](end_span)
            }
        }
        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true // Archives JAR[span_5](end_span)
            }
        }
    }
}
