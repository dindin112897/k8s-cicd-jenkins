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
                    welcome("Geraldine","Tuesday")
                    helloWorldExternal(name:"Geraldine", dayOfWeek:"Tuesday")
                    buildDocker.myAppNpm()
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
