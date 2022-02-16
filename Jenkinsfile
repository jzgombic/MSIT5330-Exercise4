podTemplate(containers: [
    containerTemplate(
        name: 'jnlp', 
        image: 'jenkins/inbound-agent:4.3-4'
        )
  ]) {

        node(POD_LABEL) {
        
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
        }
}
