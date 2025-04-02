pipeline {
    agent any

    environment {
        PIP_PATH = 'C:\\Users\\surjeeth\\AppData\\Local\\Programs\\Python\\Python313\\Scripts\\pip.exe'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Aravindak27/SE_Final.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '"$PIP_PATH" install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python -m unittest discover -s tests'
            }
        }

        stage('Post Results') {
            steps {
                junit 'test-reports/*.xml'
            }
        }
    }
    
    post {
        always {
            echo 'Cleaning up workspace...'
            deleteDir() // Cleans up the workspace after execution
        }
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Build or tests failed. Check the logs for details.'
        }
    }
}
