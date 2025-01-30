pipeline {
	options {
		buildDiscarder(logRotator(numToKeepStr: '3', artifactNumToKeepStr: '1'))
		disableConcurrentBuilds abortPrevious: true
	}

	agent {
		docker {
			image 'docker.dev.dbeaver.infra/jenkins-builder'
			reuseNode true
		}
	}

	stages {
		stage("Clean up after build") {
			steps {
				script {
                    PR_author = sh (
                        script: "gh pr view ${env.CHANGE_ID} --json author --jq '.author.login' -R https://github.com/aboutgh/about-pub",
                        returnStdout: true
                    ).trim()					
					echo PR_author
				}
			}
		}
	}
}
