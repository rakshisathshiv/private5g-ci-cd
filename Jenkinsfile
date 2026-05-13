pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/rakshisathshiv/private5g-ci-cd'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 jenkins-app'
            }
        }
    }
}
