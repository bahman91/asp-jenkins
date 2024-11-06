pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Starting Checkout from branch master...'              
                git branch: 'main', url: 'https://github.com/bahman91/asp-jenkins.git'              
                echo 'Checkout completed successfully!'
            }
        }
        stage('Restore') {
            steps {           
                echo 'Starting package restore...'             
                bat 'dotnet restore'              
                echo 'Restore completed successfully!'
            }
        }
        stage('Build') {
            steps {            
                echo 'Starting build process...'             
                bat 'dotnet build --configuration Release'               
                echo 'Build completed successfully!'
            }
        }
        stage('Test') {
            steps {          
                echo 'Starting unit tests...'             
                bat 'dotnet test'            
                echo 'Tests completed successfully!'
            }
        }
        stage('Publish') {
            steps {         
                echo 'Starting publish process...'            
                bat 'dotnet publish --configuration Release --output ./publish'             
                echo 'Publish completed successfully!'
            }
        }
    }
}
