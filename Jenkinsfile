//Declarative
pipeline{
	//agent any
	   //agent { docker { image 'maven:3.9.9'} }
	   agent { docker { image 'node:23.2'} }
		stages {
			stage('build') {
				steps {
					sh 'node --version'
					echo "Build"	
			}
		}
			stage('Test') {
				steps {
					echo "Test"
				}
			}
			stage('Integration Test') {
				steps {
					echo "Integration Test"	
			}
		}
	}
	
	post {
		always {
			echo 'i am awesome , i run always'
		}
		success {
			echo 'i Run when you are successful'
		}
		failure {
			echo 'i run when you fail'
		}
	}
	
}
