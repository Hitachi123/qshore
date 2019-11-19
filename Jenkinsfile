pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Hitachi123/qshore.git', branch: 'master', credentialsId: 'narendrasingamaneni91')
      }
    }

    stage('compile') {
      parallel {
        stage('compile') {
          steps {
            bat 'mvn compile'
          }
        }

        stage('unit-test') {
          steps {
            bat 'mvn test'
          }
        }

        stage('package') {
          steps {
            bat 'mvn package'
          }
        }

      }
    }

    stage('deploy') {
      parallel {
        stage('deploy') {
          steps {
            bat 'REM TEST'
          }
        }

        stage('deploy1') {
          steps {
            bat 'REM TEST1'
          }
        }

      }
    }

    stage('selenium') {
      steps {
        bat 'REM Automation'
      }
    }

  }
}