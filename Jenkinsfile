pipeline {
  agent any

  stages {
    stage("Start") {
      steps {
        sh "curl -sS getcomposer.org/installer | php"
        sh "php composer.phar install"
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
