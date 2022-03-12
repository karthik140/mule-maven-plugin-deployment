pipeline{
	agent any{
		stages{
			stage('Build Application'){
				bat 'mvn clean install'
			}
			stage('Munit Testing Application'){
				bat 'mvn test'
			}
			stage('Deploy Application'){
				bat 'mvn package deploy -Ptest -DmuleDeploy'
			}
		}
	}
}
