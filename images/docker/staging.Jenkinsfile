pipeline {
  agent any
  options {
    timeout(time: 10, unit: 'MINUTES')
  }

  parameters {
      string(name: 'ARTIFACT_ID', defaultValue: 'staging', description: '')
  }
  options {
      timeout(time: 2, unit: 'MINUTES')
  }

  stages {
  stage('Prebuild') {
      steps {
            sh '''echo "FROM $ARTIFACT_ID" > Dockerfile'''
            sh "vercel build"
          }
      }
  }
  stage('Publish') {
      steps {
          script {
              withCredentials([string(credentialsId: 'NOW_TOKEN', variable: 'NOW_TOKEN')]) {
                  sh '''vercel deploy --prebuilt --token $NOW_TOKEN --name nodeapp --confirm'''
              }
          }
      }
  }

    post { 
        always { 
            cleanWs()
        }
    }
  }
}
