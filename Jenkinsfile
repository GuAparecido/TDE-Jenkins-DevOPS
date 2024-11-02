pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }

        stage('Build Containers') {
            steps {
                script {
                    // Constrói os containers definidos no docker-compose.yml
                    sh 'docker compose down -v'
                    sh 'docker compose build'
                }
            }
        }

        stage('Start Application') {
            steps {
                script {
                    // Inicia os containers
                    sh 'docker compose up -d'
                }
            }
        }
    }
}
