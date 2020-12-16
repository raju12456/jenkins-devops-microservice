pipeline 
{
	agent any
	stages {
		stage('Build') {
			steps {
				echo "Build"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
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
