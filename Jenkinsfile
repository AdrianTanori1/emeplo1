pipeline {
    agent any
 
    stages {
        stage('Instalar Dependencias') {
            steps {
                script {
                    // Instala las dependencias del proyecto
                    bat 'npm install'
                }
            }
        }
 
        stage('Construir y Desplegar') {
            steps {
                script {
                    // Ejecuta el script de inicio de la aplicación
                    bat 'npm start'
                }
            }
        }
    }
}