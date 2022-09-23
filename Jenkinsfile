pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/venkykukatla/Docker.git']]])
            }
        }
        stage('Dokcker version') {
            steps {
               script{
               sh "sudo docker version"
                
               }    
            }
        } 
        stage('Dokcker images') {
            steps {
               script{
               sh "sudo docker images"
                
               }    
            }
        }   
            stage('Dokcker build') {
            steps {
               script{
               sh "sudo docker build -t m1 ."
                
               }    
            }
        } 
        stage('Dokcker tag') {
            steps {
               script{
               sh "sudo docker tag m1:latest vkukatla/docker:v11"
                
               }    
            }
        }  
        stage('Dokcker imagess') {
            steps {
                script{
                sh "sudo docker images"
                
               }    
            }
        }
        stage('Dokcker push to hub') {
            steps {
                script{
                sh "sudo docker push vkukatla/docker:v11"
                
               }    
            }
        }                                                

    }   
}
