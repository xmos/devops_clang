pipeline {
  agent {
    label 'some_builder'
  }
  environment {
  }
  options {
    skipDefaultCheckout()
  }
  stages {
    stage('Checkout') {
      sh """git clone https://llvm.org/git/llvm.git"""
      dir("llvm") {
        dir("tools") {
          checkout scm
          dir("clang") {
            dir("tools") {
              sh """git clone https://llvm.org/git/clang-tools-extra.git extra"""
            }
          }
        }
      }
    }
    stage('Build') {
    }
    // stage('Test') {
    // }
  }
  post {
  }
}
