#!/user/bin/env groovy

pipeline{
    agent any

    stages{
        stage("build image"){
            script{
                echo 'building image..'
                withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]){
                    sh "docker build -t deepakmohap81/demo-app:my-app-3.0 ."
                    sh 'echo $PASS | docker login -u $USER --password-stdin'
                    sh "docker push deepakmohap81/demo-app:my-app-3.0"
                }
            }
        }
    }




}