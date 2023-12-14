pipeline {
    agent any //bisa juga di kasih di stage
    environment {
        AUTHOR = "Ichwan Dwi Nursid"
        EMAIL = "vV6xq@example.com"
    }
    parameters {
        string(name: "NAME", defaultValue:"Guest", description: "What is your name?")
        text(name: "NAME", defaultValue:"Guest", description: "What is your name?")
        booleanParam(name: "TOGGLE", defaultValue: true, description: "Toggle this value")
        choice(name: "CHOICE", choices: ["One", "Two", "Three"], description: "Pick something")
        password(name: "PASSWORD", defaultValue: "SECRET", description: "Enter a password")
    }
    stages {
         stage("prepare"){
            steps {
                echo "start jonb : ${env.JOB_NAME}"
                echo "start build : ${env.BUILD_NUMBER}"
                echo "Branch Name : ${env.BRANCH_NAME}"
                script {
                    def buildDisplay = currentBuild.getDisplayName()
                    echo "build display : ${buildDisplay}"
                }
            }
        }
        stage("Build"){
            environment {
                APP = credentials("my-password") // get from jenkins credentials 
            }
            steps {
                echo "username = ${APP_USR}" // username di beri suffx USR akan di reject
                echo "password = ${APP_PSW}" // password di beri suffx PSW akan di reject
                echo "Hello Build"
                sleep(5)
                echo "Hello Build"
                script {
                    for (int i = 0; i < 10; i++) {
                        echo "Hello ${i}"
                    }
                }
                sh 'echo "app password = $APP_PSW" > "rahasia.txt"'
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
                sh "ls -la"
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