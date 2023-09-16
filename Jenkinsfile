@Library('java_sharedlib')
pipeline{
    agent any

    stages{
        stage('Git Checkout'){
            steps{
                script{
                    gitCheckout(
                        branch: "main"
                        url: "https://github.com/tahatalha/java_app.git"
                    )
                }
            }
        }
    }
}