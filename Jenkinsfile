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
  
    node(kubeagent) {
        stages {
            stage('build') {
                steps {
                    sh 'mvn --version'
                }
            }
        }
    }
}
