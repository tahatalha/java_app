@Library('jenkins_shared_lib') _
pipeline{
    agent any
    
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description:'Choose Create/Destroy')
    }

    stages{
        
        stage('Git Checkout'){
            when { expression { param.action == 'create' } }
            steps{
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/AdvanceCodeMarshall/mrdevops_java_app.git"
                )
            }
        }
        stage('Unit Test maven'){
            when { expression { param.action == 'create' } }
            steps{
                script{
                    mvnTest()
                }
            }
        }
        stage('Integeration Test maven'){
            when { expression { param.action == 'create' } }
            steps{
                script{
                    mvnIntegerationTest()
                }
            }
        }
        stage('Static Code Analysis : Sonarqube'){
            when { expression { param.action == 'create' } }
            steps{
                script{
                    staticCodeAnalysis()
                }
            }
        }
    }
}