pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=neonecorp_neonesec -Dsonar.organization=neonecorp -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=bb0f08d43d98cad9ff39042292a0910391d817dd'
			}
        } 
  }
}