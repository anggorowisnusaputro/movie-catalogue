pipeline {
    agent any
    stages {
        stage("Build"){
            steps {
               nodejs('nodejs14'){
                   sh 'npm install'
                   sh 'npm run build'
               }
            }
        }
        stage("Test"){
            steps {
                echo "Testing"
            }
        }
        stage("Deploy"){
            steps {
                echo "Deploying"
            }
        }
    }
}