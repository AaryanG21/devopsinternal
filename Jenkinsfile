pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven' 
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/AaryanG21/devopsinternal.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        
        
       
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }

}
