pipeline{
    agent any
    stages {
        stage('build') {
            steps {
                echo "build"
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