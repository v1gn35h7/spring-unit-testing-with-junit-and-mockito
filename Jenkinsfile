pipeline {
    agent any

    environment {
        // You can set environment variables here
        MAVEN_OPTS = "-Dmaven.test.failure.ignore=true"
    }
   
    stages {
       
        stage('Build & Test') {
            steps {
                sh 'mvn clean test'
            }
        }

        stage('Publish Test Results') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
        
      
    }
    


    post {
        always {
            echo 'Pipeline completed.'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
