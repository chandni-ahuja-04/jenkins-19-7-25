pipeline {
  agent any
  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/chandni-ahuja-04/jenkins-19-7-25.git'
      }
    }
    stage('Package index.html') {
      steps {
        sh 'zip -r index.zip chandni/index.html'
      }
    }
    stage('Upload to S3') {
      steps {
        sh 'aws s3 cp index.zip s3://chandni-bucket/'
      }
    }
  }
}
