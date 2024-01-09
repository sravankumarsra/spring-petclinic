pipeline{
	agent {label 'jdk17'}
	stages {
	stage('checkout'){
		steps{	
		git url : 'https://github.com/sravankumarsra/spring-petclinic.git', branch : 'main'
	  }
	}
	stage('build the code and sonarqube analysis') {
		steps{
	sh script: '/opt/maven/bin/mvn clean'
		//withSonarQubeEnv('sonar'){
		//sh script: '/opt/maven/bin/mvn clean'
		//}
		}
	}
	stage('Archieving and Reporting'){
		steps{
		junit testResults: 'target/surefire-reports/*.xml'
		archiveArtifacts artifacts: '**/*.jar'
		}
	}
	}
	post{
	success {
		echo "success" 
	}
	}
}
