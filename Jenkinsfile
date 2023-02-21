pipeline {
    agent any
    stages {
        stage('Checkout code from git'){
                    steps{
                        git 'https://github.com/ShubhamDiwan/New_Docker_Project.git'
                    }
                }
        stage('Build Application') {
            steps {
                sh 'mvn -f pom.xml clean package'
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
