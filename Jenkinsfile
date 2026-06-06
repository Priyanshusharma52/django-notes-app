@Library("shared") _
pipeline {
    agent {label "Jenkins-agent"}

    stages {
        stage ("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code") {
            steps {
                script{
                clone("https://github.com/Priyanshusharma52/django-notes-app.git", "main")
                }
            }
        }

        stage("Build") {
            steps {
                script {
                    Buildimage("notes-app", "latest")
                }
            }
        }

        stage("Push to DockerHub") {
            steps {
                script {
            docker_push("notes-app", "latest", "priyanshusha")
        }
    }
                }
            
        

        stage("Deploy") {
            steps {
               script {
                   docker_deploy()
               }
        }
        }
        }
}
