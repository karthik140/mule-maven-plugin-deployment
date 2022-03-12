Pipeline 
{
	agent any{
		stages{
			stage('Build Application'){
				Steps{
					bat 'mvn clean install'
					}
			}
			stage('Munit Testing Application'){
				steps{
					bat 'mvn test'
					}
			}
			stage('Deploy Application'){
				steps{
					bat 'mvn package deploy -Ptest -DmuleDeploy'
					}
			}
		}
	}
}
