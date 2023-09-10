@Library('jenkins_shared_lib') _
pipeline{
    agent any
    
    parameters{
        choice(name: 'action', choices: 'create\ndelete', description:'Choose Create/Destroy')
    }

    stages{

        stage('Git Checkout'){
            when { expression { params.action == 'create' } }
            steps{
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/AdvanceCodeMarshall/mrdevops_java_app.git"
                )
            }
        }
        stage('Unit Test maven'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    mvnTest()
                }
            }
        }
        stage('Integeration Test maven'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    mvnIntegerationTest()
                }
            }
        }
        stage('Static Code Analysis : Sonarqube'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    def SonarQubecredentialsId = 'sonarqube-api'
                    staticCodeAnalysis(SonarQubecredentialsId)
                }
            }
        }
        stage('Quality Gate Status Check : Sonarqube'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    def SonarQubecredentialsId = 'sonarqube-api'
                    qualityGateStatus(SonarQubecredentialsId)
                }
            }
        }
        stage('Maven Build : maven'){
            when { expression { params.action == 'create' } }
            steps{
                script{
                    mvnBuild()
                }
            }
        }
    }
}