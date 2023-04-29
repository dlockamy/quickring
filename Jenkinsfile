def remote = [:]
remote.allowAnyHosts = true

pipeline {
	agent any;

	stages {
		stage('Log Deploy Details'){
			steps {
                script {
                	echo "(Re)deploy Quickring Container"
            	}
        	}
        }
    	stage('Update Source, Run Docker-Compose'){
            steps {
                script {
                    sshagent(credentials : ['dlockamy_ssh']) {
                        sh "ssh -T -o StrictHostKeyChecking=no dlockamy@$192.168.0.104 \" \
                            pwd; \
                            whoami; \
                            \""
                    }
                }
            }
        }
    }
}
