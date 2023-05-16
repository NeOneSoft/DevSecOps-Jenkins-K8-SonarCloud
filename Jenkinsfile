pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=neonecorp_neonesec -Dsonar.organization=neonecorp -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=954b724166f57ab4cb64d53e35b40b279ed9383e'
			}
        } 
  }
}
