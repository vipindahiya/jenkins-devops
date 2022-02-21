pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	enviroment{
		dockerHome = tool'myDocker'
		mavenHome = tool'myMaven'
		PATH = "$dockerHome/bin:mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
			}
		}
		stage('Test'){
			steps{
				echo "test"
			}			
		}
		stage('Integration test'){
			steps{
				echo "Integration test"
			}
		}
	}
	post{
		always{
			echo "Always"
		}
		success{
			echo "Success"
		}
		failure{
			echo "Failed"
		}
	}
}
