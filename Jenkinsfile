@Library('shared') _
pipeline {

    agent { label 'dev-server' }

    stages {

        stage("Code Clone") {
            steps {
                sh "whoami"
                script {
                    clone(
                        "https://github.com/LondheShubham153/django-notes-app.git",
                        "main"
                    )
                }
            }
        }

        stage("Code Build") {
            steps {
                script {
                    dockerbuild()
                }
            }
        }

        stage("Push to DockerHub") {
            steps {
                script {
                    dockerpush()
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
