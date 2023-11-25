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
                    // Instalamos las dependencias y ejecutamos el servidor web
                    bat 'npm install'
                    bat 'start /B npm start'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Aquí puedes agregar pasos adicionales de implementación si es necesario
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
