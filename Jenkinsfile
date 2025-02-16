pipeline {
  agent any
  stages {
    stage('Check Version') {
      steps {
        sh 'echo Print Maven Version'
        sh 'mvn --version'
      }
    }

    stage('Build') {
      steps {
        sh 'mvn clean package -DskipTests=true'
        archiveArtifacts 'target/hello-demo-*.jar'
      }
    }

    stage('Test') {
      steps {
        sh 'mvn test'
        junit(testResults: 'target/surefire-reports/TEST-*.xml', keepProperties: true, keepTestNames: true)
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo Deploying using ArgoCD'
      }
    }

  }
  tools {
    maven 'M3'
  }
}