pipeline {
    agent any
    tools {
        node 'node-25'
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


