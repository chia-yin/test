pipeline {
  agent any

  stages {

    options {
      ansiColor('xterm')
    }

    stage("Start") {
      steps {
        sh "composer install"
        sh "pwd"
      }
    }
    
    stage("Running") {
      steps {
        sh "php artisan test"
      }
    }
    
    stage("End") {
      steps {
        sh "echo End > /tmp/End.txt"
      }
    }
  }
}
