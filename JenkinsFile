
pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install checkstyle:checkstyle pmd:pmd findbugs:findbugs'
      }
    }
    stage('Clean Workspace') {
      steps {
        cleanWs()
      }
    }
  }
}
