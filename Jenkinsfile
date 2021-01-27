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
	// agent { 
	// 	docker{
	// 		image 'node:13.8' 
	// 		//image 'maven:3.6.3'
	// 		//args '-u root --privileged' 
	// 	} 
	// }
	environment{ 
		dockerHome =  tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps{
				sh 'mvn --version'
				//sh 'node --version'
				//sh 'docker version'
				echo "Build"
				echo "Path  - $PATH"
				echo "Build_Number - $env.BUILD_NUMBER"
				echo "Build_Id - $env.BULID_ID"

			}
		}
		stage('Compile'){
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
