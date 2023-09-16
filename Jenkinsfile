pipeline{
    agent any

    stages{
        stage('Git Checkout'){
            steps{
                script{
                    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/tahatalha/java_app.git']])
                }
            }
        }
    }
}