pipeline {
  agent {
    docker {
        image 'saucelabs/stt-puppeteer-jest-node:v0.1.8'
    }
  }
  environment {
    SAUCE_USERNAME = credentials('sauce-username')
    SAUCE_ACCESS_KEY = credentials('sauce-access-key')
    CI = true
  }
  stages {
    stage('Run Saucectl Puppeteer Tests') {
      steps {
        // This step trigger the tests
        sh 'saucectl run -c ./.sauce/puppeteer.yml --verbose'
      }
    }
  }
}