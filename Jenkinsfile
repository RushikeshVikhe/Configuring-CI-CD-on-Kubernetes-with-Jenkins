pipeline {
  agent any
  stages {
    stage('Docker Build') {
      steps {
        sh "docker build -t kmlaydin/podinfo:${env.BUILD_NUMBER} ."
      }
    }
}
post {
    success {
      slackSend(message: "Pipeline is successfully completed.")
    }
    failure {
      slackSend(message: "Pipeline failed. Please check the logs.")
    }
}
}
