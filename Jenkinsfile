pipeline{
	agent {label 'jdk17'}
	stages {
	stage('checkout'){
		steps{	
		git url : 'https://github.com/sravankumarsra/spring-petclinic.git', branch : 'main'
	  }
	}
	stage('build the code') {
		steps{
		sh: script: '/opt/maven/mvn package'
		}
	}
	stage('Reporting'){
		steps{
		junit testResults: 'target/surefire-reports/*.xml'
		archiveArtifacts artifacts: '**/*.jar'
		}
	}
	}
}
