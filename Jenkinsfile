podTemplate(containers: [
    containerTemplate(
        name: 'jnlp', 
        image: 'jenkins/inbound-agent:4.3-4'
        )
  ]) {

        node('kubeagent') {
            stage('Build a Maven Project') {
                git 'https://github.com/spring-projects/spring-petclinic.git'
                sh '''
                echo 'Maven Build'
                '''   
            }   
        }       
}
