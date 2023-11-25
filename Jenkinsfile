pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

    stage('Build and Run') {
        steps {
        script {
                // Especifica la ruta completa al ejecutable de Node.js
                bat '"C:\\Program Files\\nodejs\\node.exe" -v'
            
                // Ejecutar npm install express
                bat '"C:\\Program Files\\nodejs\\npm" install express || true'
            }
        }
    }
        stage('Check Node.js and npm versions') {
            steps {
                script {
                    bat 'node -v'
                    bat 'npm -v'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Agrega aquí pasos adicionales de implementación si es necesario
                    echo 'Implementación completa'
                }
            }
        }
    }

    post {
        always {
            // Esto se ejecutará siempre, incluso si hay errores
            script {
                // Detener el servidor web después de completar la construcción
                bat 'taskkill /F /IM node.exe'
            }
        }
    }
}

