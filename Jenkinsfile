pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis.') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=neonecorp_neonesec -Dsonar.organization=neonecorp -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=42b7521c6e42aa7113ca4aa70140a1229f0cdebc'
			}
        } 
  }
}
