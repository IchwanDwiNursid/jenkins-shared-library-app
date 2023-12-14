pipeline {
    agent any
    environment {
        AUTHOR = "Ichwan Dwi Nursid"
        EMAIL = "vV6xq@example.com"
    }
    stages {
         stage("prepare"){
            steps {
                echo "start jonb : ${env.JOB_NAME}"
                echo "start build : ${env.BUILD_NUMBER}"
                echo "Branch Name : ${env.BRANCH_NAME}"
            }
        }
        stage("Build"){
            steps {
                echo "Hello Build"
                sleep(5)
                echo "Hello Build"
                script {
                    for (int i = 0; i < 10; i++) {
                        echo "Hello ${i}"
                    }
                }
            }
        }

        stage("Test"){
            steps {
                echo "Hello Test"
                sleep(5)
                echo "Hello Test"
                script {
                    def data = [    // object pakeknya array
                        "firstName" : "Ichwan",
                        "lastName" : "Nursid"
                    ]

                    writeJSON(file: "data.json", json: data)
                }
            }
        }

        stage("Deploy"){
            steps {
                echo "AUTHOR = ${AUTHOR}"
                echo "EMAIL = ${EMAIL}"
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