properties([
  buildDiscarder(
      logRotator(
          numToKeepStr: '30'
      )
  )
])

pipeline {
  agent {
    label master
  }

  post {
    /* clean up our workspace */
    always {
      dir(WORKSPACE_DIR) {
        deleteDir()
      }
    }
    /* end of clean up our workspace */

    success {
      echo "success"
    }

    failure {
      echo "failed"
    }
  }
}
