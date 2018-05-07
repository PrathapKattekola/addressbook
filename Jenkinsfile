pipeline {
    agent any
      stages{
         stage('checking Code'){
             steps {
               echo " This Stage Check Code in the remote repository"
               sleep 2
	     }
         }
          stage('Cleaning the target Folder'){
             steps{
                 echo " This stage is concerned in cleaning the target folder"
                 sh 'mvn clean'
             }
           }
          stage('testing the code'){
            steps {
  		echo "This stage is concerned on code analysis"
		sh 'mvn test'
            }
          }
          stage('Packaging of code'){
             steps { 
               echo " This stage makes the war file"
               
               sh 'mvn package'
             }
          }
          stage('Archive Artifacts'){
            steps {
              echo "Archeving Artifacts . . . "
              archiveArtifacts artifacts: '**/target/*.war'
              echo "Well Done - Finished Archeving "
              
            }
          }        
           stage('Deploying'){
             steps{
               echo "This process deploy the code in local Repository"
               sh 'mvn install'
               
             }
		   
	   }
		   
	 stage('Own-test'){
             steps{
               echo "This process deploy the code in local Repository"
               sh 'echo $dtr'
               
          }
	 }   }
}
