pipeline {
    agent any

    stages {
        stage('Source (Clone)') {
            steps {
                // This pulls your code from GitHub
                git 'https://github.com/Leigha1234/runcalc-app-ci.git'
            }
        }

        stage('Build (Docker)') {
            steps {
                // This tells Jenkins to use your Dockerfile to build the app
                sh 'docker build -t runcalc-app:latest .'
            }
        }

        stage('Test (Success Check)') {
            steps {
                // This checks if the image actually exists after the build
                sh 'docker images | grep runcalc-app'
                echo 'CI Part 1 Complete: Docker image built successfully.'
            }
        }
    }

    post {
        always {
            echo 'CI Process Finished.'
        }
    }
}
