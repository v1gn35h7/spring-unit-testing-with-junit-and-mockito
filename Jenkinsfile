pipeline {
    agent any

    environment {
        // You can set environment variables here
        MAVEN_OPTS = "-Dmaven.test.failure.ignore=true"
    }

      tools {
        maven 'Maven 3'  // Define your Maven installation name from Jenkins Global Tool Configuration
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
