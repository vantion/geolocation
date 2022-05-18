pipeline {

 triggers {
  pollSCM ('* * * * *')
}
    agent any
    tools {
  maven 'M2_HOME'
}

    stages {
        stage('maven package') {
            steps {
                sh 'mvn clean'
                sh 'mvn install'
                sh 'mvn package'
                sleep 5
            }
        }
         stage('test') {
            steps {
                sh 'mvn test'
            }
        }
         stage('deploy') {
            steps {
                echo 'deploy step'
                sleep 10
            }
        
        }
    }
}