pipeline {
  agent {
    node {
      label 'maven'
    }
    
  }
  stages {
    stage('build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('unit test') {
      steps {
        echo 'testing'
      }
    }
    stage('deploy') {
      steps {
        sh 'mvn fabric8:deploy'
      }
    }
    stage('promote-qa') {
      steps {
        sh 'oc tag myproject/demo:latest myproject/demo:qa'
      }
    }
  }
}