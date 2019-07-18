pipeline {
    agent any
	
	environment {
	         DEPLOYABLE_BRANCH = ${env.BRANCH_NAME ==~ /(^master).*/}
			}

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
		    when {
			       expression { "$DEPLOYABLE_BRANCH".toBoolean() }
				 }
            steps {
                echo 'Deploying....'
				script {
				   sh 'helm install ./helm --tiller-namespace development --namespace development --name test'
				   }
               }
            }
        }
    }
