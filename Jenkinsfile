#!groovy
node {
  ansiColor('xterm') {
  timestamps {

  stage('Prepare') {
    checkout scm
    sh 'docker ps'
    sh 'docker images'
  }
  stage('Build') {
    sh 'docker-compose build'
  }
  stage('Test') {
    try {
      sh 'docker-compose run client'
    } catch (Exception e) {
      throw e;
    } finally {
      sh 'docker-compose logs'
      sh 'docker-compose down --remove-orphans || true'
    }
  }

  }
  }
}
