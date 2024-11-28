pipeline {
	agent any
	//agent { docker { image 'node:13.8'} }
	stages{
		stage('Build') {
			steps{
				//sh 'mvn --version'
				//sh 'node --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.Build_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD TAG - $env.Build_TAG"
				echo "BUILD URL - $env.Build_URL"
			}
			
		}
		stage('Test') {
			steps{
				echo "Test"
			}
			
		}
		stage('Integration Test') {
			steps{
				echo "Integration Test"
			}
			
		}

	} 
	post{
		always{
			echo 'I am awesome'
		}
		success{
			echo 'I run when you are successful'
		}
		failure{
			echo 'I run when you fail'
		}
	}
	
}
