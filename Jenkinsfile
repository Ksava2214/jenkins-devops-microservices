//Declarative
pipeline{
	agent any
		stages {
			stage('build') {
				steps {
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
		always{
			echo 'i am awesome , i run always'
		}
		Success{
			echo 'i Run when you are successful'
		}
		failure{
			echo 'i run when you fail'
		}
	}
	
}
