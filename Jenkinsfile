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
                git branch: 'master', url: 'https://github.com/egbea123/Ansible_Playbook.git'
            }
         }
         stage('Ansible Deploy') {    
            steps { 
                 ansiblePlaybook installation: 'ansible_server', playbook: 'tomcatdeploy/site.yaml'
            }
        }
   }
   	 
}
