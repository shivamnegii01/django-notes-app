@Library('shared') _
pipeline {

    agent { label 'vinod' }

    stages {

        stage("Hello") {
            steps {
                script {
                    hello()
                }
            }
        }

        stage("Code Clone") {
            steps {
                script {
                    clone(
                        "https://github.com/shivamnegii01/django-notes-app.git",
                        "main"
                    )
                }
            }
        }

        stage("Build") {
            steps {
                script {
                    docker_build()
                }
            }
        }

        stage("Push to DockerHub") {
            steps {
                script {
                    docker_push()
                }
            }
        }

        stage("Deploy") {
            steps {
                script {
                    deploy()
                }
            }
        }
    }
}
