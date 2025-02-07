// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }
pipeline {
	agent any
	// agent { docker {image 'node:23.7' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$PATH:$dockerHome/bin:$mavenHome/bin"
	}
	stages {
		stage('checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker --version'
				echo 'Building..'
				echo "$PATH"
				echo "BUILD_NUMBER: ${BUILD_NUMBER}"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
			}
		}
		stage('compile') {
			steps {
				sh 'mvn clean compile'
			}
		}
		stage('test') {
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}
	post {
		always {
			echo 'This will always run'
		}
		success {
			echo 'This will run only if successful'
		}
		failure {
			echo 'This will run only if failedaaaa111'
		}
	}
}