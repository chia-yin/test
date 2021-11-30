pipeline {
  agent any

  stages {
    stage("Start") {
      steps {
        sh "curl -sS https://getcomposer.org/installer | php56"
        sh "cd ~/bin"
        sh "ln -s /usr/local/bin/php56 php"
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
