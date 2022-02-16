podTemplate(containers: [
    containerTemplate(
        name: 'jnlp',
        image: 'jenkins/inbound-agent:4.3-4',
        )
  ],
    
  volumes: [
  persistentVolumeClaim(
      mountPath: '/root/.m2/repository', 
      claimName: 'jenkins-pv-claim', 
      readOnly: false
      )
  ]) 

{
  
    node(POD_LABEL) {
        stage('Get a Maven project') {
            git
            'https://github.com/dlambrig/simple-java-maven-app.git'
            container('jnlp') {
                stage('Build a Maven project') {
                      sh '''
                      echo "Maven build"
                      mvn -B -DskipTests clean package
                      '''
                }
            }
        }
    }
}
