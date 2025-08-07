pipeline {
    agent { label 'java-agent' }

    environment {
        MAVEN_HOME = '/usr/share/maven'
    }

    stages {
        stage('Clone Code') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git'
            }
        }

        stage('Build with Maven') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            echo '❌ Build failed.'
        }
    }
}

