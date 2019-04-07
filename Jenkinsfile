pipeline {
    agent any
    stages {
       stage('Build') {
           steps {
		   node('master'){
               sh 'mvn clean package'
			   sh label: '', script: 'sudo docker image build -t devi .'
			   sh label: '', script: 'sudo docker login -u admin -p admin123 34.213.35.158:8082'
			   sh label: '', script: 'sudo docker tag devi:latest 34.213.35.158:8082/devi:1.0.1'
			   sh label: '', script: 'sudo docker push 34.213.35.158:8082/devi:1.0.1'
			   }
		   node('slave1'){	
		       sh label: '', script: 'sudo docker login -u admin -p admin123 34.213.35.158:8082'
		       sh label: '', script: 'sudo docker pull 34.213.35.158:8082/devi:1.0.1'
			   sh label: '', script: 'sudo docker container run -it -d -p 8888:8080 devi:latest'
           }
		}
		
    }  
}
}
  
