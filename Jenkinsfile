pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        checkout scm
        sh "composer install"
        sh "cp .env.example .env"
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
