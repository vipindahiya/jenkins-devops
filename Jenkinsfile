pipeline {
	//agent any
	agent { docker { image 'maven:3.6.3'} }
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
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
