pipeline {
    agent any

    environment {
        // You can set environment variables here
        MAVEN_OPTS = "-Dmaven.test.failure.ignore=true"
    }
   
    stages {
        stage('Checkout') {
            steps {
                // Pull code from Git repository
                git url: 'git@github.com:v1gn35h7/spring-unit-testing-with-junit-and-mockito.git', branch: 'master'
            }
        }

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
