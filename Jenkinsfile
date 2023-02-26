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
                sh 'mvn spring-boot:run'
            }
            post {
                success {
                    echo "Now Archiving the Artifacts...."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('Build and create docker image'){
            steps{
                sh "docker build . -t newdockerimage:${env.BUILD_ID}"
            }
        }
    }
}
