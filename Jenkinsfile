pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build code, docker Image & helm chart'
				script {
				   sh 'helm install ./helm --tiller-namespace development --namespace development --name test'			}
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
