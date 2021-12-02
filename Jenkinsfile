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
    
    stage("End") {
      steps {
        junit 'report.xml'
      }
    }
  }
}
