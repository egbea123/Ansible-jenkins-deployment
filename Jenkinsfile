pipeline {	 
    agent any	 
   	 stages {     	 
   	 stage("Compile") {          	 
   			 steps {               	 
   				 sh "mvn compile"          	 
   			 }     	 
   		 }     	 
   	 stage(" Testing ") {          	 
   		 steps {               	 
   				 sh "mvn test"          	 
   			 }     	 
   		 }
	 stage("build and package") {          	 
   		 steps {               	 
   				 sh "mvn clean package"          	 
   			 }     	 
   		 }
        stage('checkout') {
           steps {    
               // git branch: 'master', url: 'https://github.com/egbea123/Ansible_Playbook.git'
		 git 'https://github.com/egbea123/Ansible_Playbook'
            }
         }
         stage('Ansible Deploy') {    
            steps { 
                 echo "PATH is: $ANS_HOME"
                 sh "whoami"
                 sh "echo $PATH"
		 ansiblePlaybook credentialsId: '84259fbb-0403-473e-9ae2-2d8105d57402', disableHostKeyChecking: true, installation: 'ansible_server', playbook: 'tomcatdeploy/site.yaml'    
	    }
        }
   }
   	 
}
