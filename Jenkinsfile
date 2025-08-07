pipeline {
    agent { label 'java-agent' }

    environment {
        MAVEN_HOME = '/usr/share/maven'
    }

    stages {
        stage('Build with Maven') {
            steps {
                echo "🔧 Building the app..."
                sh 'mvn clean install'
            }
        }

        stage('Run Tests') {
            steps {
                echo "🧪 Running tests..."
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            echo '✅ Pipeline completed.'
        }
    }
}

