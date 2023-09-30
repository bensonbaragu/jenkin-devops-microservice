//Scripted syntax - Old way. 
//Declarative is the new way. 
pipeline {
		agent any
		//Using docker image as an agent
		//agent { dockerContainer { image 'node:alpine3.17'} }

		// environment {
		// 	dockerHome = tool "myDocker"
		// 	mavenHome = tool "myMaven"
		// 	PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		// }
		stages {
			stage('Checkout'){
				steps{
					//sh 'node --version'
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH - $PATH"
					echo "BUILD_NUMBER - $env.BUILD_NUMBER" 
					echo "BUILD_ID - $env.BUILD_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
					echo "BUILD_URL - $env.BUILD_URL"
				}
			}
			stage('Compline'){
				steps{
					sh "mvn clean compile"
				}
			}
			stage('Test'){
				steps{
					sh "mvn test"
				}
			}
			stage('Integration Test'){
				steps{
					sh "mvn failsafe:integration-test failsafe:verify"
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

