pipeline {

    agent any

 

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

                    docker.image('python:latest').inside {

                        sh 'pip install -r requirements.txt' // Example if you have requirements.txt

                        sh 'python test.py' // Replace with your actual run command

                    }

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
