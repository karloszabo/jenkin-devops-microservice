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
	stages {
		stage ("Build") {
			spteps {
				echo "Build"
			}
		}
		stage ("Test") {
		spteps {
			echo "Test"
			}
		}
		stage ("Integration Test") {
			spteps {
				echo "Integration Test"
			}
		}		
	}
}

