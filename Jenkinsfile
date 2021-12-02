pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        git "https://github.com/chia-yin/test.git"
        checkout scm
        sh "composer update"
      }
    }
    
    stage("Running") {
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
