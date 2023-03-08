pipeline {
    agent any
      
    stages {
        stage('Checkout code from git'){
                    steps{
                        git 'https://github.com/ShubhamDiwan/New_Docker_Project.git'
                    }
                }
        stage(' Java Version') {
                    steps {
                        sh 'java --version'
                    }
                }
        stage('Build Application') {
            steps { 
                sh './mvnw clean install -P buildDocker'
            }
        }
        stage('Run Docker Image'){
           steps{
              sh 'cd /root/.jenkins/workspace/petclinic_project'
              sh 'COMPOSE_HTTP_TIMEOUT=600 docker-compose up'
           }
        }
        stage('Open Application'){
           steps{
              sh 'firefox -new-tab http://127.0.0.1:8888'
              sh 'firefox -new-tab http://127.0.0.1:8761'
              sh 'firefox -new-tab http://127.0.0.1:9091'
              sh 'firefox -new-tab http://127.0.0.1:3000'
              sh 'firefox -new-tab http://127.0.0.1:9090'
              sh 'firefox -new-tab http://127.0.0.1:9411'
           }
        }
    }
}
