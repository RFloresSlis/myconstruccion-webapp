pipeline {
    agent any
    tools {
        maven 'Maven 3.9'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/RFloresSlis/myconstruccion-webapp.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'target/*.war', fingerprint: true
        }
    }
}
