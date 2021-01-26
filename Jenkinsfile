//DECLARATIVE
// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// 	stage('Integration Test'){
// 		echo "Test"
// 	}
// }

//SCRIPTED

pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
				echo "Build"
			}
		}
		stage('Test'){
			steps{
				echo "Build"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
	}
	post{
		always{
			echo "I run always"
		}
		success{
			echo "I run on success"
		}
		failure{
			echo "I run on fail"
		}
	}
}
