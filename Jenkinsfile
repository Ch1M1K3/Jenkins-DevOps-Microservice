pipeline {
	agent any 
	// agent { docker { image 'maven:3.6.3' } }
	// agent { docker { image 'node:13.8' } }
	environment {
		dockerHome = tool 'MyDocker'
		mavenHome = tool 'MyMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage ('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				// sh 'docker help'
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

		stage ('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}

		stage ('Test') {
			steps {
				sh "mvn test"
			}
		}
		
		stage ('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
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

