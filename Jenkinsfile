pipeline {
  enviroment {
    registry = 'jaabayron/flask_app'
    registryCredentials = 'docker'
    cluster_name = 'skillstorm'
  }
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/fatleladle/flasking3', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t jaabayron/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u jaabayron -p dckr_pat_9vlS5P45fPFsDnnftEcV4hWVTOg'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push jaabayron/flask_app '
      }
    }

  }
}