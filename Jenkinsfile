pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
               bat 'mvn clean install -B -DskipTests'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}