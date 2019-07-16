pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build code, docker Image & helm chart'
				script {
				   sh(script: helm install ./helm --tiller-namespace development --namespace development --name test,returnStatus: true) == 0
				}
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}