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
			stage('Checkout') {
				steps {
					sh 'docker version'
					sh 'mvn --version'
					echo "Build"	
			 }
			}
			stage( 'Complile' ) {
				steps {
				 sh "mvn clean compile"
			}
		  }
		  	stage('Package'){
				steps{
					sh "mvn package -DskipTests"
				}
			}
		
			stage('Build Docker Image') {
				steps {
					script{
						dockerImage = docker.build("ksava2214/currency-exchange-devops:22}")
					}
				}
			}
			stage('Push Docker Image') {
				steps {
					script{
						docker.withRegistry('','dockerhub') {
							dockerImage.push();
							dockerImage.push('latest');
						}
					}
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
