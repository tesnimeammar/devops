pipeline {

  agent any

    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']],
                        userRemoteConfigs: [[
                            credentialsId: 'c57ca164-2d55-4a45-8f29-b685bed8a6d7',
                            url: 'https://github.com/tesnimeammar/devops.git']]])
                }
            }
        }
        
	stage('Install') {
           steps{
              script{
                   sh "sudo npm install"
                }
            }
        }

	stage ('Build') {
	     steps {
	 	 script{
			sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
	
			}
		    }

	}







	}




}
