pipeline {
    agent any
    stages {
        stage("Clone code") {
            steps {
                echo "cloning"
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Bigyan1021/frozenyogurtshop.git'
            }
        }
        stage("Build Image") {
            steps {
                echo "Building"
                sh "docker build -t bigyankc1021/frozen-webapp:main ."
            }
        }
        stage("Push Image to repoistory") {
            steps {
                echo "Pushing Image"
                withCredentials([usernamePassword(credentialsId:"dockerhub",passwordVariable:"password",usernameVariable:"user")]){ 
                sh "docker tag frozen-webapp ${env.user}/frozen-webapp:main"
                sh "docker login -u ${env.user} -p ${env.password}"
                sh "docker push ${env.user}/frozen-webapp:main"
                }
            }
        }
        stage("ssh into server") {
            steps {
                sshagent(['ssh']){
                     sh 'ssh -o StrictHostKeyChecking=no ubuntu@44.223.34.253 "cd /home/ubuntu/frozenapp && docker compose up -d . "'
                }
            }
        }
    }
}