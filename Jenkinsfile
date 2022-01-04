
pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install checkstyle:checkstyle pmd:pmd findbugs:findbugs'
      }
    }
  }
  post {
    always {
      recordIssues(
        enabledForFailure: true, aggregatingResults:true,
        tools: [java(), checkStyle()]
      )
    }
  }
}
