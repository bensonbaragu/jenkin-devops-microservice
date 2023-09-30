//Scripted syntax - Old way. 
//Declarative is the new way. 
pipeline {
		agent any
		//Using docker image as an agent
		//agent { dockerContainer { image 'node:alpine3.17'} }
		stages {
			stage('Build'){
				steps{
					//sh 'node --version'
					echo "Build"
					echo "PATH - $PATH"
					echo "BUILD_NUMBER - $env.BUILD_NUMBER" 
					echo "BUILD_ID - $env.BUILD_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
					echo "BUILD_URL - $env.BUILD_URL"
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

