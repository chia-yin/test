pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        git "https://github.com/chia-yin/test.git"
        checkout scm
        sh (script: "curl -sS https://getcomposer.org/installer")
        sh (script: "mv composer.phar /usr/local/bin/composer")
        sh (script: "/usr/local/bin/composer install")
        sh (script: "cp .env.example .env")
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
