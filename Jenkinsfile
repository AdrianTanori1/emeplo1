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
                // Cambia al directorio donde se encuentra tu archivo package.json
                dir('C:\\Users\\atanori\\Documents\\UTH\\emeplo1') {
                    script {
                        try {
                            // Ejecuta npm start
                            bat '"C:\\Program Files\\nodejs\\node.exe" app.js || true'
                        } catch (Exception e) {
                            // Manejo de errores
                            echo "Error: ${e.message}"
                        }
                    }
                }
            }
        }
    }
}
