node {
    docker.image('maven:3.8.5-eclipse-temurin-8-alpine').inside {
        stage('Build') {
            sh 'mvn -B -DskipTests clean package'
        }
        stage('Test') {
            checkout scm
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
        }
    }
}