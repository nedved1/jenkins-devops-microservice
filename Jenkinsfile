// node {
// 		echo "Build"
// 		echo "Test"
// 		echo "Test"
// }
pipeline {
	// agent any
	agent { docker {image 'maven:3.6.3' } }
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