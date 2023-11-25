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
                    // Agrega la ruta de instalación de Node.js a la variable de entorno PATH
                    bat 'SET PATH=C:/Program Files/nodejs;%PATH%'
                    
                    // Ahora deberías poder ejecutar el comando npm
                    bat 'npm install'
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

