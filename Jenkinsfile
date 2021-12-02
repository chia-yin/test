pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        git "https://github.com/chia-yin/test.git"
        checkout scm
        sh "composer install --ignore-platform-reqs"
      }
    }
    
    stage("Testing") {
      steps {
        sh "vendor/bin/phpunit --log-junit report.xml"
      }
    }
    
    stage("Report") {
      steps {
        junit 'report.xml'
      }
    }

    post {
      success {
        sh "echo success"
      }
      failure {
        sh "echo failure"
      }
    }
  }
}
