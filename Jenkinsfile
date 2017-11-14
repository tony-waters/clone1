// see https://dzone.com/refcardz/declarative-pipeline-with-jenkins for examples

pipeline {
  agent any
  stages {
    stage("Checkout Code") {
      steps {
        checkout scm
      }
    }
    stage("Build with Maven") {
      steps {
        sh "mvn clean"
        sh "mvn install"
      }
    }
    stage("Create docker image") {
        steps {
            sh "docker build -t $registry/clone1:master ."
            sh "docker push $registry/clone1:master"
        }
    }
  }
}