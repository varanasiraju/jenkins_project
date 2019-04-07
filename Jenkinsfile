pipeline {
    agent any
    stages {
        stage ('package stage') {
            steps {
			node ('master') {
               sh 'mvn clean package'
			   sh label: '', script: 'sudo docker image build -t devi .'
			   sh label: '', script: 'sudo docker login -u admin -p admin123 54.213.128.20:8082'
			   sh label: '', script: 'sudo docker tag devi:latest 54.213.128.20:8082/devi:1.0.5'
			   sh label: '', script: 'sudo docker push 54.213.128.20:8082/devi:1.0.5'
			   }
			node('slave1') {
			   sh label: '', script: 'sudo docker login -u admin -p admin123 54.213.128.20:8082'
			   sh label: '', script: 'sudo docker pull 54.213.128.20:8082/devi:1.0.5'
			   sh label: '', script: 'sudo docker container run -it -d -p 9999:8080 54.213.128.20:8082/devi:1.0.5'
			   }   
               
            }
        }
    }
}
