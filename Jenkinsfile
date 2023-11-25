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
                bat '"C:\\Program Files\\nodejs\\npm" run start || true'
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
}