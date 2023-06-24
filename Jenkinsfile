pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('build ') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn clean install'
        }

      }
    }

    stage('Results') {
      steps {
        junit '**/target/surefire-reports/TEST'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}