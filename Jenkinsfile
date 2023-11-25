pipeline {
    agent any

    stages {
        stage('listo') {
            steps {
                checkout scm
            }
        }

    stage('comprobar') {
        steps {
        script {
                // Especifica la ruta completa al ejecutable de Node.js
                bat '"C:\\Program Files\\nodejs\\node.exe" -v'
            
                // Ejecutar npm install express
                bat '"C:\\Program Files\\nodejs\\npm" install express || true'
                // Ejecución del servidor Node.js
                bat '"C:\\Program Files\\nodejs\\npm" start || true'
            }
        }
    }
}
    stage('iniciar') {
        steps {
        script {
                bat '"C:\\Program Files\\nodejs\\npm" start || true'
            }
        }
    }
}