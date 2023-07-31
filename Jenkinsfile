pipeline {
  agent any
  stages {
    stage('stage1') {
      agent any
      environment {
        env = 'prd'
      }
      steps {
        git(poll: true, url: 'https://github.com/Kumarobin/known-Blueocean.git', branch: 'main')
      }
    }

    stage('stage2') {
      parallel {
        stage('stage2') {
          steps {
            git(url: 'https://github.com/Kumarobin/known-Blueocean.git', branch: 'main', poll: true)
            echo 'Hello world'
          }
        }

        stage('stage2.1') {
          steps {
            sh 'whoami'
          }
        }

      }
    }

    stage('stage3') {
      steps {
        sleep 300
        sleep 300
      }
    }

    stage('stage4') {
      steps {
        sleep 500
      }
    }

  }
}