pipeline{
    agent any
    stages('Git Checkout'){
        steps{
            script{
                git branch: 'main', url: 'https://github.com/AdvanceCodeMarshall/mrdevops_java_app.git'
            }
        }
    }
}