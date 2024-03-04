pipeline {
    agent any  
    stages {
        stage("checkout") {
            steps {
                checkout scm
            }
        }

        stage("Test") {
            steps {
                // Assuming npm is already installed on the Jenkins agent
                sh 'npm test'
            }
        }

        stage("Build") {
            steps {
                sh 'npm run build'
            }
        }

        stage("Build docker image"){
            steps {
                sh 'docker build -t node-app:1.0 .'
            }    
        }
    }
}
