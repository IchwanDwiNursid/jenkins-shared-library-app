@Library("jenkins-shared-library@main") _

import ichwan.jenkins.Output




pipeline {
    agent any 
    stages {
        stage("Hello Groovy") {
            steps {
                script {
                    Output.hello(this,"Groovy")
                }
            }
        }
        stage("function") {
            steps {
                script {
                    author.name()
                    author.channel()
                }
            }
        }
        stage("Hello World") {
            steps {
                script {
                    hello.world()
                }
            }
        }
        stage("Library resource") {
            steps {
                script {
                    def config = libraryResource("config/build.json") 
                    echo(config)
                }
            }
        }
    }
}