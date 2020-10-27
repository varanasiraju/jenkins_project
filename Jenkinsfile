pipeline {
    agent { label 'master' }
    stages {
        stage ('Compile') {
            steps {
                sh 'mvn package'
            }
        } 
    }
}
