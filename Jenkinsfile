pipeline {
	agent any
	stages{
		stage('Build'){
			steps{
				echo "Build"
			}
		}
		stage('Test'){
			echo "test"
		}
		stage('Integration test'){
			echo "Integration test"
		}
	}
	post{
		always{
			echo "Always"
		}
		sucess{
			echo "Sucess"
		}
		failure{
			echo "Failed"
		}
	}
}
