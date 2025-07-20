pipeline {
  agent any
  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/<your-username>/cicd-nginx-deploy.git'
      }
    }
    stage('Package index.html') {
      steps {
        sh 'zip -r index.zip rushi/index.html'
      }
    }
    stage('Upload to S3') {
      steps {
        sh 'aws s3 cp index.zip s3://your-s3-bucket-name/'
      }
    }
  }
}
