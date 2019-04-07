pipeline {
    agent any
    stages {
        stage ('package stage') {
            steps {
                sh 'mvn clean package'
				sh label: '', script: 'java -jar target/*.jar'
            }
        }
    }
}