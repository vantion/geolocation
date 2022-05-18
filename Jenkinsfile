pipeline {

    agent any
    tools {
  maven 'M2_HOME'
}

    triggers {
  pollSCM '* * * * *'
}
checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vantion/geolocation.git']]])

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