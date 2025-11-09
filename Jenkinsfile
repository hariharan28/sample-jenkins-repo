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
        stage('Approval to Deploy') {
            steps {
                script {
                    def userInput = input(
                        id: 'ProceedConfirmation', message: 'Do you want to deploy?', parameters: [
                            [$class: 'BooleanParameterDefinition', defaultValue: false, description: 'Check to proceed with deployment', name: 'Proceed']
                        ]
                    )
                    if (!userInput) {
                        error("Deployment aborted by user.")
                    }
                }
            }
        }
        stage('Deploy Code') {
            steps {
                sh 'cp * /Users/Shared/html/' // Adjust path based on your setup
            }
        }
    }
}
