pipeline {
    agent any

    stages {
        stage('Branch Info') {
            steps {
                echo "🚀 Build untuk branch: ${env.BRANCH_NAME}"
            }
        }

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    def imageName = "hello-multibranch:${env.BRANCH_NAME}"
                    sh "docker build -t $imageName ."
                }
            }
        }

        stage('Test') {
            steps {
                echo "✅ Simulasi test berhasil untuk ${env.BRANCH_NAME}"
            }
        }
    }
}
