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
              container('jnlp') {
                  stage('Shell Execution') {
                      sh '''
                      echo "Hello! I am executing shell"
                      '''
                  }
              }
        }
    }
}
