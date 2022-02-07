//using declarative approach
//using docker as an agent

pipeline {
	agent { docker {image 'maven:3.6.3'}}
	stages{
		stage ('Build'){
			steps{
					sh 'mvn --version'
					echo "Build"
			}
		}
		stage ('Test'){
			steps{
					echo "Test"
			}
		}
		stage ('Integration Test'){
			steps{
					echo "Integration"
			}
		}
	}
	post {
		always {
				echo 'I am awesome. I always run'
		}
		success {
				echo "I run only when you are successful"
		}
		failure{
				echo " i only run when there is a failure"
		}
		changed {
				echo "status don change sir"
		}
	}
}
