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
   }
   	 
}
