pipeline {
    agent any
    stages { 
        stage('checkout SCM') {
            steps {
                echo 'SCM check out Done Successfully'
            }
        }
        stage('Maven Build') {
            steps {
                echo 'Maven Build done Successfully'
            }
        }  
        stage('SonarQube Analysis') {
            steps {
                echo 'sonar Annalysis is completed'
            }
        }
        stage('Nexus upload') {
            steps {
                echo 'NEXUS upload is completed'
            }
        }  
    }
}
