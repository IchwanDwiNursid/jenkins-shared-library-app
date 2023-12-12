pipeline {
    agent any
    stages {
        stage("Build"){
            steps {
                echo "Hello Build"
            }
        }

        stage("Test"){
            steps {
                echo "Hello Test"
            }
        }

        stage("Deploy"){
            steps {
                echo "Hello Deploy"
                sh "error"
            }
        }
    }
    post {
       always {
        echo "always"
       }
       success {
        echo "success"
       }
       failure {
        echo "failure"
       }
    }
}