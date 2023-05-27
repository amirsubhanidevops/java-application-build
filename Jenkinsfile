@Library('my-shared-library') _
pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/amirsubhanidevops/java-application-build.git"
                )
            }
        }

        stage('Unit Testing') {
            steps {
                script{
                    mvnTest()
                }
            }
        }

        // stage('Integration Testing') {
        //     steps {
        //         script{
        //             mvnTest()
        //         }
        //     }
        // }
    }
}
