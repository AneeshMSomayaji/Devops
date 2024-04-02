pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'pip install -r https://github.com/AneeshMSomayaji/Devops/blob/main/requirements.txt'
                sh 'https://github.com/AneeshMSomayaji/Devops/blob/main/demo.py'
            }
        }
        stage('Dockerize') {
            steps {
                script {
                    docker.build('demo:latest')
                }
            }
        }
    }

    post {
        success {
            echo 'Build and Dockerization successful!'
        }
        failure {
            echo 'Build or Dockerization failed!'
        }
    }
}
