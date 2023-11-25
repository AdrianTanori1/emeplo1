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
                    // Agrega la ruta de Node.js al sistema
                    bat 'SET PATH=C:/Program Files/nodejs;%PATH%'
            
                    // Ahora deberías poder ejecutar el comando npm
                    bat 'npm run start'  // Usa '|| true' para que la ejecución no falle si npm devuelve un código de error
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

