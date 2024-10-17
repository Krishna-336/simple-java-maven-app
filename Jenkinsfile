pipeline {
    agent any
    tools {
        maven 'maven' 
    }
    stages {
        stage('Building My Java App') { 
            steps {
                echo "This is stage used to build my source code"
                sh "mvn package"
                
            }
        }
    }
}
