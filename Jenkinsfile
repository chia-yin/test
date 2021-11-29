pipeline {
  agent any

  stages {
    stage("Start") {
      steps {
        sh "echo Start > /tmp/Start.txt"
      }
    }
    
    stage("Running") {
      steps {
        sh "echo Running > /tmp/Running.txt"
      }
    }
    
    stage("End") {
      steps {
        sh "echo End > /tmp/End.txt"
      }
    }
  }
}
