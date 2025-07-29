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
                    def safeBranch = env.BRANCH_NAME.replaceAll(/[^a-zA-Z0-9_.-]/, '-')
                    def imageName = "hello-multibranch:${safeBranch}"
                    echo "🔧 Membangun Docker image dengan tag: $imageName"
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
