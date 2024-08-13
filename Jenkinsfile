pipeline {
agent any
	environment {
		ANYPOINT_CREDS = credentials('ANYPOINT_CREDENTIALS')
	}
	stages {
		stage('Build') {
			steps {
				bat 'mvn clean install'
			}
		}
		stage('Test') {
			steps {
				bat 'mvn test'
			}
		}
		stage('Deployment') {
			steps {
				bat 'mvn deploy -DmuleDeploy -Danypoint.username="%ANYPOINT_CREDS_USR%" -Danypoint.password="%ANYPOINT_CREDS_PSW%"'
			}
		}
	}
}

