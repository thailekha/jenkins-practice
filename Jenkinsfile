pipeline {
    agent { docker 'node:6.3' }
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

        post {
            always {
                echo 'This will always run'
            }
            success {
                echo 'This will run only if successful'
            }
            failure {
                echo 'This will run only if failed'
            }
            unstable {
                echo 'This will run only if the run was marked as unstable'
            }
            changed {
                echo 'This will run only if the state of the Pipeline has changed'
                echo 'For example, if the Pipeline was previously failing but is now successful'
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