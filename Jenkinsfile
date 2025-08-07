pipeline {
    agent { label 'java-agent' }

    stages {
        stage('Clone Code') {
            steps {
                git url: 'https://github.com/rayudu-gangadhara-rao/spring-petclinic.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh './mvnw clean package -DskipTests'
            }
        }

        stage('Run Tests') {
            steps {
                sh './mvnw test'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully.'
        }
        failure {
            echo '❌ Build failed.'
        }
    }
}

