// Scripted
//node {
//	stage('Build') {
//		echo "Build"
//	}
//	stage('Test') {
//		echo "Test"
//	}
//	stage('Integration Test') {
//		echo "Integration Test"
//	}
//}
//Declarative
pipeline {
	agent any 
	// agent { docker {image 'maven:3.6.3'}}
	// agent { docker {image 'node:13.8'}}
	environment {
		dockerHOME = tool "myDocker"
		mavenHOME = tool "myMaven"
		PATH = "$dockerHOME/bin:$mavenHOME/bin:$PATH"
	}
	stages {
		stage ("Checkout") {
			steps {
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
		stage ("Compile") {
			steps {
				sh "mvn clean compile"
			}
		}
		stage ("Test") {
			steps {
				sh "mvn test"
			}
		}
		stage ("Integration Test") {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}		
	} 
	
	post {
		always {
			echo 'Im awesome. I run always'
		}
		success {
			echo 'I run when you are succesful'
		}
		failure {
			echo 'I run when you are fail'
		}
	}
}

