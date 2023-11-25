pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Especifica la ruta completa al ejecutable de Node.js
                    bat '"C:\\Program Files\\nodejs\\node.exe" -v'
                
                    // Ejecutar npm install express
                    bat '"C:\\Program Files\\nodejs\\npm" install express || true'
                }
            }
        }

        stage('Build and Run') {
            steps {
                script {
                    // Ejecución del servidor Node.js
                    bat '"C:\\Program Files\\nodejs\\npm" run start || true'
                }
            }
        }
    }
}