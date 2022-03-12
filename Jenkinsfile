pipeline
{
	agent any
	environment {
    //adding a comment for the commit test
    ANYPOINT_CREDS = credentials('ANYPOINT_CREDENTIALS')
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
		environment {
   			 CLIENT_ID = credentials('DEV_CLIENT_ID')
   			 CLIENT_SECRET = credentials('DEV_CLIENT_SECRET')
  		}
			steps{
				bat 'mvn package deploy -DskipTests -Ptest -DmuleDeploy -Dusername="%ANYPOINT_CREDS_USR%" -Dpassword="%ANYPOINT_CREDS_PSW%" -Danypoint.platform.client_id="%CLIENT_ID%" -Danypoint.platform.client_secret="%CLIENT_SECRET%"                                '
				}
		}
		
		
	}
}