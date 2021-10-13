pipeline {
	agent any
	tools {
		maven "m3"
	}
	stages {
		stage ('git') {
			steps {
				git 'https://github.com/ILyaAX/boxfuse-origin-1.git'
			}
		}
		stage ('build') {
			steps {
				sh 'mvn package'
			}
		}
		stage ('deploy') {
			steps {
				deploy adapters: [tomcat9(credentialsId: 'df6fde50-0c49-4062-b9c9-f173a97f3a85', path: '', url: 'http://89.208.199.239:8080/')], contextPath: 'web', war: '**/*.war'
			}
		}
	}
}