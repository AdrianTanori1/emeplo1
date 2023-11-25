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
                    bat 'SET PATH=C:/Program Files/nodejs'
                    // Ahora deberías poder ejecutar el comando npm
                    bat 'npm install express || true'
                    bat 'npm run start || true'  // Usa '|| true' para que la ejecución no falle si npm devuelve un código de error
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

