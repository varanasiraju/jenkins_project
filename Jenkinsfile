pipeline {
    agent { label 'master' }
    stages {
        stage ('Compile') {
            steps {
                sh 'mvn package'
                sh label: '', script: 'sudo java -jar /var/lib/jenkins/workspace/Delixus/target/spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar &'
            }
        } 
    }
}
