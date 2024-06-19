pipeline {
    agent {
        dockerContainer { image 'ss24531/jenkins-python-agent:latest' }
    }
    triggers {
    pollSCM('* * * * *')
}
    stages {
        stage("Checkout") {
            steps {
                git url: 'https://github.com/s24531/Jenkins_12_zad1.git', branch: 'main'
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

