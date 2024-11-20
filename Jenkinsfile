//Declarative
pipeline{
	agent any
	   //agent { docker { image 'maven:3.9.9'} }
	   //agent { docker { image 'node:23.2'} }
	   environment {
			dockerHome = tool 'MyDocker'
			mavenHome = tool 'My_Maven'
			PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	   }
		stages {
			stage('build') {
				steps {
					sh 'docker version'
					sh 'mvn --version'
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
