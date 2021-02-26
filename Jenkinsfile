pipeline {
  environment {
    registry = "inamdarsaifu/docker_test"
    registryCredential = 'dockerhub'
    dockerImage = ''
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
		script {
		dockerImage = docker.build registry + ":$BUILD_NUMBER"
		}
            }
	}
        stage('Push Docker Image') {
            steps {
                echo 'Push Docker Image Step'
        	script {
          		docker.withRegistry( '', registryCredential ) {
            		dockerImage.push()
          		}
		}
            }
	}
	    
    }
    
}
