node {

   stage('SCM') {
      // git clone
	  git 'https://github.com/GitPracticeRepo/spring-petclinic.git'
   }
   
   stage ('build the packages') {
      // mvn package
	  sh 'mvn package'
	  sh label: '', script: 'java -jar target/*.jar'
   }

   
   
   stage ('archival') {
     // archiving artifacts
	 archive 'target/*.jar'
   }

}