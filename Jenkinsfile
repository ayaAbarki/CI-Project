pipeline {
    agent any
    stages {
        stage('Clonage') {
            steps {
                git branch: 'main',
                url: 'https://github.com/ayaAbarki/CI-Project.git'
            }
        }
        stage('Vérification Python') {
            steps {
                bat 'python --version'
                bat 'python -m pip --version'
            }
        }
        stage('Installation des dépendances') {
            steps {
                bat 'python -m pip install -r requirements.txt'
            }
        }
        stage('Tests Unitaires') {
            steps {
                bat 'python -m pytest'
            }
        }
    }
    post {
        always {
            echo 'Pipeline terminé.'
        }
        success {
            echo 'BUILD SUCCESS'
        }
        failure {
            echo 'BUILD FAILURE'
        }
    }
}