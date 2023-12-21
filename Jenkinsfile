pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    docker.build('flora')
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    docker.withRegistry('https://hub.docker.com/', 'sivajid788@gmail.com,7816062R@') {
                        docker.image('flora').push()
                    }
                }
            }
        }
}
}
