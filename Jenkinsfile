@Library('java_sharedlib') _

pipeline{
    agent any

    stages{
    
        stage('Git Checkout'){

            steps{
                script{
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/tahatalha/java_app.git"
                    )
                }
            }
        }
        stage('Unit Test Maven'){

            steps{
                script{
                    mvnTest()
                }
            }
        }
        stage('Integration Test Maven'){

            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }
        stage('StaticCodeAnalysis Maven'){

            steps{
                script{
                    staticCodeAnalysis()
                }
            }
        }
    }
}