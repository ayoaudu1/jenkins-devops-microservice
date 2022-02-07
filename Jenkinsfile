//using declarative approach
//using docker as an agent

pipeline {
	agent any
	//agent {docker{image 'maven:3.8-jdk-11'}}
	environment {
		
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage ('Checkout'){
			steps{
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "PATH - $PATH"
					echo "BUILD_NUM - $env.BUILD_NUM"
					echo "BUILD_ID - $env.BUILD_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
					echo "BUILD_URL - $env.BUILD_URL"

			}
		}
		stage ('Compile'){
			steps{
				sh "mvn clean compile"

			}
		}
		stage ('Test'){
			steps{
				sh "mvn test"
			}
		}
		stage ('Integration Test'){
			steps{
					sh "mvn failsafe: integration-test failsafe:verify"
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
		changed{
				echo "status don change sir"
		}
	}
}
