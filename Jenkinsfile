pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/Ajackson6/Flask_app.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t ajackson6/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u ajackson63 -p 7800d170-629e-4321-82ca-9701f592b581'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push ajackson63/flask_app:tagname'
      }
    }

  }
}