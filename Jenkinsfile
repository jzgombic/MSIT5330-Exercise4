podTemplate(containers: [
    containerTemplate('maven')
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
