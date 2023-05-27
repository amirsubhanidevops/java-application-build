@Library('my-shared-library') _
pipeline {
    agent any

    paramaters{
        choice(name: 'actiion', choices: 'create\ndelete', description: "Choose create or delete")
    }

    stages {
        stage('Git Checkout') {
            when( expression{ params.actiion == 'create' })
            steps {
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/amirsubhanidevops/java-application-build.git"
                )
            }
        }

        stage('Unit Testing') {
            when( expression{ params.actiion == 'create' })
            steps{
                script{ 
                    mvnTest()
                }
            }
        }
        stage('Intergration Testing') {
            when( expression{ params.actiion == 'create' })
            steps{
                script{
                    integrationTest()
                }
            }
        }

        stage('Static code analysis') {
            when( expression{ params.actiion == 'create' })
            steps{
                script{
                    staticCodeAnalysis()
                }
            }
        }

    }
}
