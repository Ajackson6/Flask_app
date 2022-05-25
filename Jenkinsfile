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
        sh 'docker login -u ajackson63 -p 6add8b77-5fef-405f-9066-34d993984b12'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push ajackson6/flask_app '
      }
    }

  }
}