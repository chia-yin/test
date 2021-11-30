pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        git "https://github.com/chia-yin/test.git"
        checkout scm
        sh "curl -sS https://getcomposer.org/installer"
        sh "sudo mv composer.phar /usr/local/bin/composer"
        sh "/usr/local/bin/composer install"
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
