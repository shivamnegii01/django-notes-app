@Library('shared') _
pipeline {

    agent { label 'vinod' }

    stages {

        stage("Hello") {
            steps {
                hello()
            }
        }

        stage("Code Clone") {
            steps {
                clone(
                  "https://github.com/shivamnegii01/django-notes-app.git",
                  "main"
                )
            }
        }
        

        stage("Build") {
            steps {
                docker_build("notes-app", "latest")
            }
        }

        stage("Push to DockerHub") {
            steps {
                docker_push("notes-app", "latest")
            }
        }

        stage("Deploy") {
            steps {
                deploy()
            }
        }
    }
}
