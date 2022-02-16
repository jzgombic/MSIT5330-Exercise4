podTemplate(containers: [
    containerTemplate(
        name: 'jnlp', 
        image: 'jenkins/inbound-agent:4.3-4'
        )
  ]) {

        node('kubeagent') {
            stage('Build a Maven Project') {
                git 'https://github.com/dlambrig/simple-java-maven-app.git'
                sh '''
                echo 'Maven Build'
                '''   
            }   
        }       
}
