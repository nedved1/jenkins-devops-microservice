// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }
pipeline {
	// agent any
	agent { docker {image 'node:latest' } }
	stages {
		stage('Build') {
			steps {
				sh 'mvn --version'
				echo 'Building..'
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