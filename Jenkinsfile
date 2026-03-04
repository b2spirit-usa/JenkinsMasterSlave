pipeline {
    agent { label 'master-node1' }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code is already checked out from GitHub'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
