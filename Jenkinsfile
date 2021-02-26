pipeline {
  environment {
    registry = "inamdarsaifu/docker_test"
    registryCredential = 'dockerhub'
  }
  agent any 
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
	}
        stage('Git Checkout') {
            steps {
                echo 'Git Repository Checkout'
		git credentialsId: 'git_cred', url: 'https://github.com/inamdarsaifu/docker_test.git'
            }
	}
        stage('Build Stage') {
            steps {
                echo 'Build Step'

            }
	}
        stage('Build Docker Image Stage') {
            steps {
                echo 'Build Docker Image Step'
		sh 'docker build -t inamdarsaifu/docker_test:2 .'

            }
	}
        stage('Push Docker Image') {
            steps {
                echo 'Push Docker Image Step'
		sh 'docker push inamdarsaifu/docker_test:2'

            }
	}
	    
	    
    }
    
}
