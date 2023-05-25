pipeline {
    agent any
    tools {
        maven 'Maven_3_5_2'
    }
    environment {
        SONAR_TOKEN = credentials('SONAR_TOKEN')
    }
    stages {
        stage('Compile and Run Sonar Analysis') {
            steps {
                sh '''
                    mvn clean verify sonar:sonar \
                    -Dsonar.projectKey=neonecorp_neonesec \
                    -Dsonar.organization=neonecorp \
                    -Dsonar.host.url=https://sonarcloud.io \
                    -Dsonar.login=${SONAR_TOKEN}
                '''
            }
        }

        stage('RunSCAAnalysisUsingSnyk') {
             steps {		
                 withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
                        sh 'mvn snyk:test -fn'
                  }
		}
        }

        stage('Build') { 
            steps { 
               withDockerRegistry([credentialsId: "dockerlogin", url: ""]) {
                 script{
                 app =  docker.build("asg")
                 }
               }
            }
        } 
    }
}
