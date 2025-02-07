// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }
pipeline {
	agent any
	// agent { docker {image 'node:23.7' } }
	stages {
		stage('Build') {
			steps {
				// sh 'node --version'
				echo 'Building..'
				echo "$PATH"
				echo "BUILD_NUMBER: ${BUILD_NUMBER}"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
			}
		}
		stage('Test') {
			steps {
				echo 'Testing..'
			}
		}
		stage('Deploy') {
			steps {
				echo 'Deploying....'
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