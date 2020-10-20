pipeline {
    agent {
        docker { 
            alwaysPull true
            image 'jonesey13/workshop-7' 
        }
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
        stage('NPM Install') {
            steps {
                dir('DotnetTemplate.Web'){
                    sh 'npm install'
                }
            }
        }
        stage('Typescript Build') {
            steps {
                dir('DotnetTemplate.Web'){
                    sh 'npm run build'
                }
            }
        }
        stage('Typescript Lint') {
            steps {
                dir('DotnetTemplate.Web'){
                    sh 'npm run lint'
                }
            }
        }
        stage('Typescript Tests') {
            steps {
                dir('DotnetTemplate.Web'){
                    sh 'npm t'
                }
            }
        }
    }
}