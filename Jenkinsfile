node {
    stage('Build') {
        docker.image('maven:3.8.5-eclipse-temurin-8-alpine').inside {
            sh 'mvn --version'
        }
    }
    stage('Test') {
        docker.image('maven:3.8.5-eclipse-temurin-8-alpine').inside {
            checkout scm
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
        }
    }
}