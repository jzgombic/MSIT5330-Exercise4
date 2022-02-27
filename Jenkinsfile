podTemplate(containers: [
  containerTemplate(
      name: 'maven', 
      image: 'maven:latest', 
      command: 'sleep', 
      args: '99d'
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
  node(POD_LABEL) {
    stage('Get a Maven project') {
      git url: 'https://github.com/dlambrig/simple-java-maven-app.git'
      container('maven') {
        stage('Build a Maven project') {
          sh '''
          echo "maven build"
          mvn -B -DskipTests clean package
          '''
        }
      }
    }
  }
}
