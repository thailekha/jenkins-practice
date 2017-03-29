node {
  stage('Build') {
    retry(3) {
      sh 'echo "Hello World"'
    }

    timeout(time: 3, unit: 'MINUTES') {
      sh '''
        echo "Multiline shell steps works too"
        ls -lah
      '''
    }
  }
}