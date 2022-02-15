podTemplate(containers: [
  containerTemplate(
      name: 'maven', 
      image: 'maven:latest', 
      command: 'sleep', 
      args: '30d'
      )
  ], 
  
  volumes: [
  persistentVolumeClaim(
      mountPath: '/root/.m2/repository', 
      claimName: 'maven-repo-storage', 
      readOnly: false
      )
  ]) 

{
  node(kube-agent) {
    stage('Build Petclinic Java App') {
      git url: 'https://github.com/spring-projects/spring-petclinic.git', branch: 'main'
      container('maven') {
        sh 'mvn -B -ntp clean package -DskipTests'
      }
    }
  }
}
