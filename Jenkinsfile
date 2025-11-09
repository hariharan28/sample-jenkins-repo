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
			     sh 'sh /opt/homebrew/bin/brew install httpd brew install httpd'
		       }
		}
		stage('Deploy Code') {
		       steps {
			     sh 'sudo cp * /var/www/html/'
		       }
		}
	}
}
