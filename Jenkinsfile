podTemplate(containers: [
    containerTemplate(
        name: 'maven',
        image: 'maven:3.8.1-jdk-8',
        command: 'sleep',
        args: '30d'
        ),
])
{
    node('kubeagent') {
        stage('Build a Maven Project') {
            git 'https://github.com/dlambrig/simple-java-maven-app.git'
            sh 'echo "Maven Build"' 
        }   
    }
}
