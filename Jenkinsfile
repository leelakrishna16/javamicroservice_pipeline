pipeline {
    agent any
    stages { 
        stage('checkout SCM') {
            steps {
                echo 'scm Checkout had started'
                git 'https://github.com/shazforiot/GOL.git'
                echo 'SCM check out Done Successfully'
            }
        }
        stage('Maven Build') {
            steps {
                echo 'Maven Build is started'
                sh 'mvn clean package'
                echo 'Maven Build done Successfully'
            }
        }
        stage ("Sonar Analysis") {
          steps {
             echo "This is SCM stage "
             def scannerHome = tool 'sonarqube'
             withSonarQubeEnv('sonarqube') {

                sh "${scannerHome}/bin/sonar-scanner \
                -D sonar.login=admin \
                -D sonar.password=leela4531 \
                -D sonar.projectkey=maven-project-javas \
                -D sonar.exclusion=vendor/**,resources/**,**/*.java \
                -D sonar.host.url=http://54.168.205.70:9000
                -D sonar.login=b970d5fc421024452e4a76576a68dc339deea699" 
          }
          }
        }
        
        stage('SonarQube Quality Check') {
            steps {
                echo 'sonar quality is started'
                
            }
        }
        stage('Nexus upload') {
            steps {
                echo 'NEXUS upload is completed'
            }
        }  
    }
}
