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
                    // Cambiar al directorio de trabajo de tu aplicación
                    dir('C:\\Users\\atanori\\Documents\\UTH\\emeplo1') {
                        // Ejecución del servidor Node.js a través de npm start
                        bat '"C:\\Program Files\\nodejs\\npm" run start || true'
                }
            }
        }
    }
}