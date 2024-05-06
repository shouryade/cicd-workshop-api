pipeline {
	agent any
	stages {
		stage('Build Docker Image') {
			steps {
				script {
					docker.build('shouryade/hono-api')
				}
			}
		}
		stage('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('https://registry.hub.docker.com', 'jenkins-docker') {
						docker.image('shouryade/hono-api').push()
					}
				}
			}
		}
	}
}
