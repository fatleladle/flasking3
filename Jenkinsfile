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
  }
}