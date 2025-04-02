pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Aravindak27/SE_Final.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh "'C:\\Users\\surjeeth\\AppData\\Local\\Programs\\Python\\Python313\\Scripts\\pip.exe' install -r requirements.txt"
            }
        }

        stage('Run Tests') {
            steps {
                sh "'C:\\Users\\surjeeth\\AppData\\Local\\Programs\\Python\\Python313\\python.exe' -m unittest discover -s tests"
            }
        }
    }
}
