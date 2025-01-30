pipeline {
	options {
		buildDiscarder(logRotator(numToKeepStr: '3', artifactNumToKeepStr: '1'))
		disableConcurrentBuilds abortPrevious: true
	}

    environment {
    	GITHUB_TOKEN = credentials('devops_gh_token_secret_text')
    }

    agent any

	stages {
		stage("Clean up after build") {
			steps {
				sh "echo main"
			}
		}
	}
}
