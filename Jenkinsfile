pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/fatleladle/flasking', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u jaabayron -p dckr_pat_7u4VcUPQUcqpTdLTScG44-YdrAU'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push flask_app'
      }
    }

  }
}