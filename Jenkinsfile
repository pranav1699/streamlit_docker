#!groovy

pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        echo 'Hello World'
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t streamlit_test_app:latest .'
      }
    }
  }
}