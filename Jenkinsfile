pipeline{
    agent any
	// agent { docker { image 'maven:3.6.3'} }
	// agent {docker {image 'node:13.8' }}
	environment {
		dockerHome = tool 'mydocker'
		mavenHome = tool 'mymaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
    stages {
        stage('build') {
            steps {
				sh 'mvn --version'
				sh 'docker --version'
                echo "build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
				echo "JOB_NAME - $env.JOB_NAME"
			}
        }
		stage('compile') {
			steps {
				sh 'mvn clean compile'
			}
		}
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Integration Test') {
            steps {
                sh 'mvn failsafe:integration-test failsafe:verify'
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