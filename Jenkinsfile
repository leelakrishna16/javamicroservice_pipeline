pipeline {
  agent any

  stages {
    stage ("Build") {
      sh 'echo "Maven Build Started"'
    }
    stage ("sonar analysis") {
      sh 'echo "sonar analysis is started and completed"'
    }
    {
      stage ("Nexus upload"){
       sh 'echo "Nexus upload is started and completed'
      }  
  }
}
