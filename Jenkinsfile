pipeline {

    agent {

        docker {image 'python:latest'}
    }

 

    stages {

        stage('Checkout') {

            steps {

                // Checkout code from the branch

                checkout scm

            }

        }

 

        stage('Build and Run in Docker') {

            steps {

                script {

                    // Build Docker image and run

                        sh 'python test.py' // Replace with your actual run command

                }

            }

        }


        stage('Code Analysis with Horusec') {

            steps {

                script {

                    // Install Horusec CLI if not already installed

                    sh 'curl -fsSL https://install.horusec.io | bash'

                    // Run Horusec scan

                    sh 'horusec start -p .'

                }

            }

        }

    }

}
