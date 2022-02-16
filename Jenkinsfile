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
        pipeline {
            agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
            stages {
                stage('build') {
                    steps {
                        sh 'mvn --version'
                    }
                }
            }
        }
    }
}
