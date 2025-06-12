pipeline {
    agent any

    tools {
        maven 'maven'
        jdk 'JKD17'
    }

    stages {
        stage('Clonar') {
            steps {
                git clone 'https://github.com/elgarj/saludoApp.git'
            }
        }

        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Probar') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'El build fue exitoso.'
        }

        failure {
            echo 'El build falló.'
        }
    }


}