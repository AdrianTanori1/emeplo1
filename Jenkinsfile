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
                
                    // Cambia al directorio donde se encuentra tu archivo package.json
                    dir('C:\\Users\\atanori\\Documents\\UTH\\emeplo1') {
                        // Ejecuta npm install express
                        bat '"C:\\Program Files\\nodejs\\npm" install express || true'
                    }
                }
            }
        }

        stage('Build and Run') {
            steps {
                script {
                    // Cambia al directorio donde se encuentra tu archivo package.json
                    dir('C:\\Users\\atanori\\Documents\\UTH\\emeplo1') {
                        // Ejecuta npm start
                        bat '"C:\\Program Files\\nodejs\\npm" start || true'
                    }
                }
            }
        }
    }
}