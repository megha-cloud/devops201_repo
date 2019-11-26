pipeline {
    agent any
    stages {
        stage('Maven Build') {
            steps {
                 sh 'mvn clean package'
            }
        }
        stage('Building Docker Image & Pushing To DockerHub'){
            steps{
                script{
                    docker.withRegistry('https://registry.hub.docker.com','dockerhub'){
                        myImage=docker.build("megha8docker/simplilearn-pipeline-repo:1.0")
                        myImage.push()
                    }    
                }
            } 
        }
    }
}
