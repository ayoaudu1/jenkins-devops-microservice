//using declarative approach
//using docker as an agent

pipeline {
	agent any
	//agent {docker{image 'maven:3.8-jdk-11'}}
	environment {
		mavenHome = tool 'myMaven'
		dockerHome = tool 'myDocker'
		
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage ('Build'){
			steps{
					sh 'docker version'
					sh 'mvn --version'
					echo "Build"
					echo "PATH - $PATH"
					echo "BUILD_NUM - $env.BUILD_NUM"
					echo "BUILD_ID - $env.BUILD_ID"
					echo "JOB_NAME - $env.JOB_NAME"
					echo "BUILD_TAG - $env.BUILD_TAG"
					echo "BUILD_URL - $env.BUILD_URL"

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
		changed{
				echo "status don change sir"
		}
	}
}
