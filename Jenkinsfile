pipeline {
    agent {
        docker { image 'jonesey13/workshop-7' }
    }
    environment {
        DOTNET_CLI_HOME = "/tmp/DOTNET_CLI_HOME"
    }
    stages {
        stage('C# Build') {
            steps {
                sh 'dotnet build'
            }
        }
        stage('C# Test') {
            steps {
                sh 'dotnet test'
            }
        }
        stage('Typescript Build') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}