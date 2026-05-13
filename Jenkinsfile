pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Vineshnayak/PyCalcCI.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python3 -m pytest'
            }
        }

        stage('Run Flask App') {
            steps {
                sh '''
                nohup python3 app.py > output.log 2>&1 &
                '''
            }
        }
    }
}