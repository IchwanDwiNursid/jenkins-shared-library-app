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
        stage("Hello World") {
            steps {
                script {
                    hello.world()
                }
            }
        }
          stage("resource groovy") {
            steps {
                script {
                    def config = libraryResource(config/build.json) 
                    echo(config)
                }
            }
        }
    }
}