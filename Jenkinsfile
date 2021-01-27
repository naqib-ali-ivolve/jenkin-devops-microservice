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
	//agent any
	agent { 
		docker{
			image 'node:13.8' 
			//image 'maven:3.6.3'
			//args '-u root --privileged' 
		} 
	}
	stages{
		stage('Build'){
			steps{
				//sh 'mvn --version'
				sh 'node --version'
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
