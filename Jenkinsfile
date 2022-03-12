pipeline
{
	agent any
	stages{
		stage('Build Application'){
			steps{
				bat 'mvn clean -DskipTests install'
				}
		}
		stage('Munit Tesing Application'){
			steps{
				bat 'mvn -DskipTests test'
				}
		}
		
		stage('Deploy Application to Mulesoft Cloudhub'){
			steps{
				bat 'mvn package deploy -DskipTests -Ptest -DmuleDeploy'
				}
		}
		
		
	}
}