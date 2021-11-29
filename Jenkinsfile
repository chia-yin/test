pipeline {
  agent any

  stages {
    stage("Start") {
      steps {
        sh "echo Start > /tmp/Start.txt"
      }
    }
    
    stage("End") {
      steps {
        sh "echo End > /tmp/End.txt"
      }
    }
  }
}
