pipeline {
    agent any
    tools {
        nodejs 'node-25'
    }
    stages {
        stage("build") {
            steps {
                echo 'Installing dependencies .....'
                sh 'npm install'
                sh 'ls -l package-lock.json'
            }
        }
    }
}




