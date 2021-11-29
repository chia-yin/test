pipeline {
  agent {
    label master
  }

  options {
    ansiColor('xterm')
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
