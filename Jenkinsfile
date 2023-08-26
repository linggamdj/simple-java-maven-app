node {
    stage('Build') {
        bat './gradlew build'
        args '-p 3000:3000'
    }
    stage('Test') {
        bat './gradlew test'
    }
}