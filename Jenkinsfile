pipeline {	 
    agent any	 
   	 stages {     	 
   	 stage("Compile") {          	 
   			 steps {               	 
   				 bat "mvn compile"          	 
   			 }     	 
   		 }     	 
   	 stage("Unit test") {          	 
   		 steps {               	 
   				 bat "mvn test"          	 
   			 }     	 
   		 }	 
   	 }

    	post {
   	 always {
   	 step([$class: 'JacocoPublisher',
   	   	execPattern: 'target/*.exec',
   	   	classPattern: 'target/classes',
   	   	sourcePattern: 'src/main/java',
   	   	exclusionPattern: 'src/test*'
   	 ])
   	 }   
    	}
}
