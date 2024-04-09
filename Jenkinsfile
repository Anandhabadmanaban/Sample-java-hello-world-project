pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { image 'maven:3.9.6-eclipse-temurin-17-alpine' }
            }
            steps {
                sh 'mvn --version'
                sh 'mvn clean -f  ./hello-app1/ package'
                  sh 'pwd'
                sh 'ls'
}
        }

        stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -f docker -t jsamplehellowroldimage:latest .'
          sh 'docker image ls'
      }
    }
        stage('Front-end') {
            agent {
                docker { image 'node:20.11.1-alpine3.19' }
            }
            steps {
                sh 'node --version'
                 sh 'pwd'
                sh 'ls'
            }
        }
    }
}
