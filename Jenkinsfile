pipeline {
    agent { docker 'mhart/alpine-node' }
    stages {
        stage('build') {
            steps {
                sh '''
                	npm --version
                    echo "Hello there"
                '''
                retry(3) {
                    sh 'retry'
                }
                timeout(time: 3, unit: 'SECONDS') {
                    sh 'timeout 3 seconds'   
                }
            }
        }
    }
}

// node {
//   try {
//     withEnv(['DISABLE_AUTH=true',
//           'DB_ENGINE=sqlite']) {
//       stage('Build2') {
//         sh 'printenv'
//       }
//     }

//     stage('Build') {
//       retry(3) {
//         sh 'echo "Hello World"'
//       }

//       timeout(time: 3, unit: 'MINUTES') {
//         sh '''
//           echo "Multiline shell steps works too"
//           ls -lah
//         '''
//       }

//       steps {
//         sh 'npm --version'
//       }
//     }
//   } catch (e) {
//     echo 'This will run only if failed'

//     // Since we're catching the exception in order to report on it,
//     // we need to re-throw it, to ensure that the build is marked as failed
//     throw e
//   } finally {
//     //echo currentBuild.getClass().getCanonicalName();
//     //echo currentBuild.getClass().getName();

//     //archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
//     //junit 'build/reports/**/*.xml'
//   }
// }
