pipeline {
    agent any

    stages {
        stage('Clonar') {
            steps {
                git 'https://github.com/usuario/mi-app.git'
            }
        }

        stage('Instalar dependencias') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Ejecutar pruebas') {
            steps {
                sh 'pytest --junitxml=report.xml'
            }
        }

        stage('Despliegue simulado') {
            steps {
                echo 'Desplegando a GCP...'
                sh 'sleep 2 && echo "¡Deploy completado!"'
            }
        }
    }

    post {
        always {
            junit 'report.xml'
        }
    }
}
