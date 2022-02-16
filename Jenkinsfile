pipeline {
    agent any
    stages {
        stage('Get a Maven Project') {
            git 'https://github.com/spring-projects/spring-petclinic.git'
            stage('Build a Maven Project') {
                sh '''
                echo 'Maven Build'
            }
        }
    }
}
