pipeline {
	agent any
	stages {
		stage('OWASP DependencyCheck') {
			steps {
				echo 'OWASP Dependency Check'
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}
