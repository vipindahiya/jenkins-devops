pipeline {
	agent any
	stages{
		stage('Build'){
			steps{
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
		sucess{
			echo "Sucess"
		}
		failure{
			echo "Failed"
		}
	}
}
