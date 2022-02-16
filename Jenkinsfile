pipeline {
    agent any
    stages {
        stage('Build a Maven Project') {
            steps {
                git 'https://github.com/spring-projects/spring-petclinic.git'
                sh '''
                echo 'Maven Build'
                '''
            }
        }
    }
}
