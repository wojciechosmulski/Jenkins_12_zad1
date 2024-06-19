pipeline {
    agent any
    triggers {
    pollSCM('* * * * *')
}
    stages {
        stage("Checkout") {
            steps {
                git url: 'https://github.com/s24531/Jenkins12_zad1', branch: 'main', credentialsId: 'github-token'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'python3 calculator.py 3 3'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'python3 test_calculator.py'
            }
        }
    }
}

