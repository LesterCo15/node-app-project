pipeline {
    agent any
    tools {
        nodejs 'node-25'
    }
    stages {
        stage("build") {
            steps {
                echo 'Installing depenencies .....'
                sh 'npm install'
            }
        }
    }
}



