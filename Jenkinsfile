pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/scavengerno1/javeedjavaproject.git'
            }
        }
        stage('Build Package') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '57f42cd2-7e34-43db-aec8-43e896a91282', path: '', url: 'http://44.220.137.4:8080/')], contextPath: 'javeedproject', war: '**/*.war'
            }
        }
    }
}

