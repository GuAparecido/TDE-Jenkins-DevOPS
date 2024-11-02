pipeline {
    agent any

    stages {
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
		    // Força a remoção do container específico se ele existir
		    sh 'docker rm -f flask_app_container'
		    sh 'docker rm -f mariadb_container'
		    // Para e remove containers antigos
		    sh 'docker compose down'
                    // Inicia os containers
                    sh 'docker compose up -d'
                }
            }
        }
    }
}
