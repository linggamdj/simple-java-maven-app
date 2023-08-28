node {
    docker.image('maven:3.9.2-eclipse-temurin-11').inside {
        stage('Build') {
            sh 'mvn -B -DskipTests clean package'
        }
        stage('Test') {
            checkout scm
            sh 'mvn test'
            junit 'target/surefire-reports/*.xml'
        }
        stage('Deploy') {
            sh './jenkins/scripts/deliver.sh' 
            input message: 'Sudah selesai menggunakan Java App? (Klik "Proceed" untuk mengakhiri)' 
            sh './jenkins/scripts/kill.sh' 
        }
    }
}