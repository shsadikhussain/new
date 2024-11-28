pipeline {
	agent any
	//agent { docker { image 'node:13.8'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages{
		stage('Build') {
			steps{
				sh 'mvn --version'
				//sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.Build_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD TAG - $env.Build_TAG"
				echo "BUILD URL - $env.Build_URL"
			}
			
		}
		stage('compile') {
			steps{
				sh "mvn clean install"
			}
			
		}
		stage('Test') {
			steps{
				sh "mvn test"
			}
			
		}
		stage('Integration Test') {
			steps{
				sh "mvn failsafe:integration-test"
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
