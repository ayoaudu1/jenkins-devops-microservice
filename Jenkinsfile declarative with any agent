//using declarative approach

pipeline {
	agent any
	stages{
		stage ('Build'){
			steps{
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
	}
}
