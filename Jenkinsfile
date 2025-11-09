pipeline {
    agent any
	stages {
		stage('Fetch Code') {
		    steps {
			   git branch: 'main', url: 'https://github.com/helpingpeopletolearn/sample-jenkins-repo.git'
		    }
		}
		stage('Install WebServer') {
		       steps {
			     sh '/opt/homebrew/bin/brew install httpd'
		       }
		}
		stage('Deploy Code') {
		       steps {
				   //Replace with a safe path or preconfigured permissions
			     sh 'cp * /Users/Shared/html/'
		       }
		}
	}
}
