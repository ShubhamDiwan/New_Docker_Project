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
                sh 'mvn -X spring-boot-maven-plugin:3.6.3:run'
            }
        }
    }
}
