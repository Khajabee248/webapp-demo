pipeline {
  agent { label 'ubuntu-slave' }   // run on the slave node with this label
  stages {
    stage('Checkout') {
      steps { checkout scm }
    }
    stage('Build') {
      steps { sh 'mvn -B -U clean package' }
    }
    stage('Archive') {
      steps { archiveArtifacts artifacts: 'target/*.war', fingerprint: true }
    }
  }
  post {
    success { echo 'BUILD SUCCESS' }
    failure { echo 'BUILD FAILED' }
  }
}
