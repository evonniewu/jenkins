pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build'
          }
        }

        stage('build1') {
          steps {
            sleep 10
          }
        }

      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'test'
          }
        }

        stage('test1') {
          steps {
            build(propagate: true, job: 'test', quietPeriod: 10, wait: true)
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploy'
          }
        }

        stage('deploy1') {
          steps {
            writeFile(file: 'deploy', text: 'Deploy Completed ', encoding: '8')
          }
        }

      }
    }

  }
}