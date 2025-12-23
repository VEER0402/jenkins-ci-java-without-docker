pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Code checked out from GitHub'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL'
        }
        failure {
            echo 'BUILD FAILED'
        }
    }
}

