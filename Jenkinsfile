pipeline {
    // Usamos un contenedor Docker con Python
    agent { docker { image 'python:3.9-slim' } } 

    stages {
        stage('Build') {
            steps {
                echo 'Construyendo el proyecto...'
            }
        }
        stage('Test') {
            steps {
                echo 'Ejecutando pruebas unitarias...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Instalando dependencias y herramientas de seguridad...'
                sh 'pip install -r requirements.txt'

                echo 'Ejecutando análisis estático con Bandit...'
                // El "|| true" permite continuar aunque Bandit encuentre vulnerabilidades
                sh 'bandit -r . || true'
            }
        }
    }
}
