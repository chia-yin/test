def setBuildStatus(String message, String state) {
  step([
      $class: "GitHubCommitStatusSetter",
      reposSource: [$class: "ManuallyEnteredRepositorySource", url: "https://github.com/chia-yin/test"],
      contextSource: [$class: "ManuallyEnteredCommitContextSource", context: "ci/jenkins/build-status"],
      errorHandlers: [[$class: "ChangingBuildStatusErrorHandler", result: "UNSTABLE"]],
      statusResultSource: [ $class: "ConditionalStatusResultSource", results: [[$class: "AnyBuildResult", message: message, state: state]] ]
  ]);
}

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
        
      post {
        success {
          setBuildStatus("Build complete!", "SUCCESS");
        }
        failure {
          setBuildStatus("Build complete!", "Failure");
        }
      }
    }
  }
}
