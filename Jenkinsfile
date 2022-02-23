pipeline {
  agent any
  stages {
    stage('compile-application') {
      steps {
        echo 'this is the build and compile job'
        sh 'npm install'
      }
    }

    stage('test-application') {
      steps {
        echo 'this is the test job'
        sh 'npm test'
      }
    }

    stage('package-application') {
      steps {
        echo 'this is the package job'
        sh 'npm run package'
      }
    }

    stage('archive-application') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}