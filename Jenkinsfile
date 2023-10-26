pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo "Before docker-compose up"
        sh 'docker-compose up'
        echo "After docker-compose up"
      }
    }
  }
}