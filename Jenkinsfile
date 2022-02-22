pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	environment{
		dockerHome = tool'myDocker'
		mavenHome = tool'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
			}
		}
		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
			}			
		}
		stage('Integration test'){
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('package'){
			steps{
				sh "mvn package -DskipTests"
			}
		}
		stage('Build Docker image'){
			steps{
				script{
					dockerimage = docker.Build("vipindahiya89/jenkins-devops:$env.BUILD_TAG")
				}				
			}
		}
		stage('Push Docker image'){
			steps{
				script{
					docker.withRegistry('','dockerhub'){
						dockerimage.push();
						dockerimage.push('latest')
					}
				}				
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
