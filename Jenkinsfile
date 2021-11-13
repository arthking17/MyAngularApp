pipeline {
	agent any
	stages{

		stage('clone and clean repo'){
			steps {
				cleanWs()
				sh "git clone -b master https://github.com/arthking17/MyAngularApp.git"
			}
		}

    stage('Build')
		{
			steps{
				script{
					sh "ansible-playbook MyAngularApp/ansible/build.yml -i MyAngularApp/ansible/inventory/host.yml"
				}
			}
		}

    stage('docker')
		{
		  steps{
		    script{
		      sh "ansible-playbook MyAngularApp/ansible/docker.yml -i MyAngularApp/ansible/inventory/host.yml"
		    }
		  }
		}

	}
}
