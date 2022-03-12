pipeline
{
	agent any
	environment {
    //adding a comment for the commit test
    //DEPLOY_CREDS = credentials('deploy-anypoint-user')
    //MULE_VERSION = '4.4.0'
   // BG = "<BUSINESS-GROUP>"
   // WORKER = "Micro"
    M2SETTINGS = "C:\\Users\\kshegu\\.m2\\settings.xml"
  }
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