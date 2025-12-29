pipeline {
    agent any
    tools {
        nodejs 'node-25'
    }
    stages {
        stage("build") {
            steps {
                script {
                    echo 'Installing dependencies .....'
                    sh 'npm install'
                    sh 'ls -l package-lock.json'
                }
            }
        }
        stage("image") {
            steps {
                script {
                    echo 'Building the image...'
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                        sh 'docker build -t lesterco/my-app:1.0 .'
                        sh 'echo $PASS | docker login -u $USER --password-stdin'
                        sh 'docker push lesterco/my-app:1.1'
                }
            }
        }
    }
        stage("deploy") {
            steps {
                script {
                    echo 'Deploying the application...'
                    sh 'docker run -p 3000:3000 lesterco/my-app:1.1' 
                }
            }
    }
}
}












