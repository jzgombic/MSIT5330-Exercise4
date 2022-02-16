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
            git 'https://github.com/cyrille-leclerc/multi-module-maven-project'
            sh 'echo "Maven Build"'
            sh 'mvn -B -DskipTests clean package'   
        }   
    }
}
