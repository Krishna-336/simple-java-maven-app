pipeline {
    agent any
    tools {
        maven 'maven' 
    }
    environment{
        docker_url = "181098/demo-pipeline"
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
                echo "This is stage used to build my source code"
                sh "docker build -t ${env.docker_url}:$BUILD_NUMBER ."
                
            }
        }
    }
}
