pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'composer install'
      }
    }

    stage('test') {
      parallel {
        stage('test') {
          steps {
            bat 'php bin/phpunit tests/unit'
          }
        }

        stage('integration') {
          steps {
            bat 'php bin/phpunit tests/integration'
          }
        }

        stage('fonctionnel') {
          steps {
            bat 'php bin/phpunit tests/fonctionnel'
          }
        }

      }
    }

  }
}