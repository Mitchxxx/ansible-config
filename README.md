
Jenkins File for Quick Task
################################################
pipeline {
    agent any

    stages {
        stage ('Initial cleanup') {
            steps{
                dir("${WORKSPACE}") {
                    deleteDir()
                }
            }

        }
        stage('Build'){
            steps{
                script{
                    sh 'echo "Building stage"'
                }
            }
        }

        stage('Test'){
            steps {
                script {
                    sh 'echo "Testing stage"'
                }
            }
        }

        stage('Package'){
            steps {
                script {
                    sh 'echo "Packaging App"'
                }
            }
        }

        stage('Deploy'){
            steps {
                script {
                    sh 'echo "Deploying App"'
                }
            }
        }

        stage('Clean Up'){
            steps{
                    cleanWs()
            }
        }
    }
}