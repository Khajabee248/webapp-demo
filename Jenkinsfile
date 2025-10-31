pipeline {
    agent any
    tools {
        maven 'MAVEN_HOME'
        jdk 'JAVA17'
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/<your-username>/webapp-demo.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
    post {
        success {
            echo '✅ Build successful!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}
