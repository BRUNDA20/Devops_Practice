pipeline {
  agent any

    stages{
         
        stage('Checkout') {
            steps {
                git "https://github.com/BRUNDA20/Devops_Practice.git"
            }
        }
        stage('Build Docker Image'){
            steps{
               script{
                   
                   def dockerImage= docker.build('my-docker-image-name:latest', '.')
               }
            }
        }
         stage('Deploy Website') {
            steps{
               script{
                   
                   dockerImage.run("-p 8080:80 --name your-container-name -d")
               }
            }
        }
    }
}
