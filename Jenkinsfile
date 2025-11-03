pipeline {
  agent any

  stages {
    stage('Checkout SCM') {
      steps {
        checkout scm
      }
    }

    stage('Parando servicios') {
      steps {
        sh 'docker compose down || true'
      }
    }

    stage('Construyendo y desplegando') {
      steps {
        sh 'docker compose up --build -d'
      }
    }
  }

  post {
    always { echo 'Pipeline finalizada.' }
    success { echo 'OK.' }
    failure { echo 'Falló.' }
  }
}
