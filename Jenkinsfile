pipeline {
    agent any
    stages {
        stage('clone'){
            steps{
               checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/olubunmi-devops/second-demo-multibranch.git']]]) 
            }
        }
        stage('Main Branch Deploy Code') {
            steps {
                sh 'echo "Building Artifact from Main branch"'
 
                sh 'echo "Deploying Code from Main Branch"'
            }
        }
        stage('Develop Branch Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                sh 'echo "Building Artifact from Develop branch"'
                sh 'echo "Deploying Code from Develop branch"'
                sh 'cat /etc/os-release'
           }
        }
    }
}
