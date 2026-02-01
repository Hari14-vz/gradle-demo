pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                [span_2](start_span)[span_3](start_span)checkout scm // Pulls from GitHub[span_2](end_span)[span_3](end_span)
            }
        }
        stage('Build & Test') {
            steps {
                [span_4](start_span)sh './gradlew clean test' // Executes Gradle build[span_4](end_span)
            }
        }
        stage('Archive Artifact') {
            steps {
                [span_5](start_span)archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true // Archives JAR[span_5](end_span)
            }
        }
    }
}
