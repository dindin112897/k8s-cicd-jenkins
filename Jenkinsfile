@Library('shared-library') _
pipeline {
    agent any
    environment {
        DOCKER_CRED = 'dockerhub'
    }
    stages {
        stage("Checkout code") {
            steps {
                checkOut()
            }
        }
        stage("Build image") {
            steps {
                script {
                    buildDocker.buildNum()
                    buildDocker.myAppDocker()
                }
            }
        }
        stage("Push image") {
            steps {
                script {
                    buildDocker.pushDocker()
                }
            }
          }        
        }
   }
