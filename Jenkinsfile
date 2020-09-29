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
	stages {
		stage ("Build") {
			steps {
				// sh 'node --version'
				echo "Build"
				echo"$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "$env.BUILD_ID"
				echo "$env.JOB_NAME"
				echo "$env.BUILD_TAG"
			}
		}
		stage ("Test") {
			steps {
				echo "Test"
			}
		}
		stage ("Integration Test") {
			steps {
				echo "Integration Test"
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

