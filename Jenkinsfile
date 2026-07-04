pipeline{
    agent any
	// agent { docker { image 'maven:3.6.3'} }
	// agent {docker {image 'node:13.8' }}
    stages {
        stage('build') {
            steps {
				// sh 'mvn --version'
				// sh 'node --version'
                echo "build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
        }
        stage('test1') {
            steps {
                echo "test1"
            }
        }
        stage('integration_test') {
            steps {
                echo "integration test"
            }
        }
    }
	post {
		always {
			echo "i am awesome.irun always"
		}
		success {
			echo "i run when i am successful"
		}
		failure {
			echo " i run when i am failure"
		}
	}
}