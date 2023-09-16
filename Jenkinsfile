@Library('java_sharedlib') _

pipeline{
    agent any

    parameters{
        choice(name: 'action', choices: 'create\ndelete', desctiption: 'choose create or delete')
    }

    stages{

        
        stage('Git Checkout'){
        when{ expression {param.action == 'create'}}
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
        when{ expression {param.action == 'create'}}
            steps{
                script{
                    mvnTest()
                }
            }
        }
        stage('Integration Test Maven'){
        when{ expression {param.action == 'create'}}
            steps{
                script{
                    mvnIntegrationTest()
                }
            }
        }
        stage('StaticCodeAnalysis Maven'){
        when{ expression {param.action == 'create'}}
            steps{
                script{
                    staticCodeAnalysis()
                }
            }
        }
    }
}