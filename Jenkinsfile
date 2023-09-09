@Library('jenkins_shared_lib') _
pipeline{
    agent any
    stages{
        stage('Git Checkout'){
            steps{
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/AdvanceCodeMarshall/mrdevops_java_app.git"
                )
            }
        }
        stage('Unit Test maven'){
            steps{
                script{
                    mvnTest()
                }
            }
        }
    }
}