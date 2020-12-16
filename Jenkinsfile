pipeline 
{
	agent any
	//agent { docker {image 'maven:3.6.3'}}

	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				sh "mvn --version"
				sh "docker --version"
				echo "Build"
				echo "$PATH"
				echo "BUILD NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "$env.JOB_NAME"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
			}
		}
		stage('Compile'){
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}
	post{
		always {
			echo "i always run.."
		}
		success{
			echo "I run on success"
		}
		failure{
			echo "I run on fail"
		}
	}
}
