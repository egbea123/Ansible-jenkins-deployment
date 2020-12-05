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
                 sh "echo $PATH"
		    sh 'ansible-playbook tomcatdeploy/site.yaml'
		}
        }
   }
   	 
}
