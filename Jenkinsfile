pipeline {
	agent any 
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:13.8' } }
	stages {
		stage ('Build') {
			steps {
				// sh 'mvn --version'
				// sh 'node --version'
				// sh 'node --help'
				echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"	
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "NODE_NAME - $env.NODE_NAME"
				echo "JENKINS_URL - $env.JENKINS_URL"
				echo "BUILD_URL - $env.BUILD_URL"
				echo "JOB_URL - $env.JOB_URL"
			}
		}
		stage ('Test') {
			steps {
				echo "Test"
			}
		}
		stage ('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	}
	
	post {
		always {
			echo 'I am awesome, I run always!!!'
		}
		success {
			echo 'I run when you are successful!!!'
		}
		failure {
			echo 'Sorry, I run when you fail!!!'
		}
	}
}

