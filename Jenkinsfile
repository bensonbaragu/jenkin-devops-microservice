//Scripted syntax - Old way. 
//Declarative is the new way. 
pipeline {
		//agent any
		//Using docker image as an agent
		agent { docker {image 'maven:3.6.3'} }
		stages {
			stage('Build'){
				steps{
					sh 'mvn --version'
					echo "Build"
				}
			}
			stage('Test'){
				steps{
					echo "Test"
				}
			}
			stage('Integration Test'){
				steps{
					echo "Integration test"
				}
			}
		} 
		post {
			always {
				echo "I am awesome. I run always"
			}
			success {
				echo "I only run when successful"
			}
			failure {
				echo "I run when you fail"
			}
		}
				
	}

