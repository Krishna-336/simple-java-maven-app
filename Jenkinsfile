pipeline {
    agent any
    tools {
        maven 'maven' 
    }
    environment{
        docker_url = "bala336/demo-pipeline"
    }
    stages {
        stage('Building My Java App') { 
            steps {
                echo "This is stage used to build my source code"
                sh "mvn package"
                
            }
        }
        stage('Building Docker Image') { 
            steps {
                echo "This is stage used to build my docker image code"
                sh "docker build -t ${env.docker_url}:$BUILD_NUMBER ."
                
            }
        }
        stage('Docker image deploy') { 
            steps {
                echo "This is used to push my docker image into to dockerhub"
                sh "docker push ${env.docker_url}:$BUILD_NUMBER"
                sh "docker rmi -f ${env.docker_url}:$BUILD_NUMBER"
                
            }
        }
        stage('Deploy image  into server') { 
            steps {
                echo "login into deploy server"
                echo "pull the latest image with BUild_number"
                echo "stop existing container"
                echo "create new conatiner with Build Number"
                   
            }
        }
        
    }
}
