pipeline {
    agent any
    tools {
      maven "M3"
    }
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
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') { 
            steps {
                sh 'echo Deploying using ArgoCD' 
            }
        }
    }
}
