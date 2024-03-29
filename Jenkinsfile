pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
                docker { image 'maven:3.9.6-eclipse-temurin-17-alpine' }
            }
            steps {
                sh 'mvn --version'
                  sh 'pwd'
                sh 'ls'
}
        }

        stage('Docker Build') {
      agent any
      steps {
        sh 'docker build . -t anandh/sample:latest'
          sh 'docker ps'
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
