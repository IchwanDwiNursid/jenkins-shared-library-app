pipeline {
    agent any
    stages {
        stage("Build"){
            steps {
                echo "Hello Build"
                sleep(5)
                echo "Hello Build"
            }
        }

        stage("Test"){
            steps {
                echo "Hello Test"
                sleep(5)
                echo "Hello Test"
            }
        }

        stage("Deploy"){
            steps {
                echo "Hello Deploy"
                sleep(10)
                echo "Hello Deploy"
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