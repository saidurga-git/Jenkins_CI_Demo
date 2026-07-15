pipeline {

    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/saidurga-git/Jenkins_CI_Demo.git'
            }
        }

        stage('Compile C Code') {
            steps {
                sh 'gcc main.c -o app'
            }
        }

        stage('Run Application') {
            steps {
                sh './app'
            }
        }

        stage('Run Python Test') {
            steps {
                sh 'python3 test.py'
            }
        }

        stage('Archive Build') {
            steps {
                archiveArtifacts artifacts: 'app'
            }
        }
    }
}
