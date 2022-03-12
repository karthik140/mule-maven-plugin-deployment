pipeline
{
	agent any
	stages{
		stage('Build Application'){
			steps{
				bat 'mvn clean install'
				}
		}
		stage('Munit Tesing Application'){
			steps{
				bat 'mvn test'
				}
		}
		
		stage('Deploy Application to Mulesoft Cloudhub'){
			steps{
				bat 'mvn package deploy -Ptest -DmuleDeploy'
				}
		}
		
		
	}
}