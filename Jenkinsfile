pipeline {
    agent any
    stages {
        stage ('checkout') {
            steps {
                git 'https://github.com/Sonal-Tiwari/devops-automation.git'
            }
        }
        stage ('install dependencies') {
            steps {
                dir('rect-beach-resort-dev') {
                    bat 'npm install'
                }
            }
        }
        stage ('Build') {
            steps {
                dir('rect-beach-resort-dev') {
                    bat 'npm run build'
                }
            }
        }
        stage ('Build image') {
            steps {
                dir('rect-beach-resort-dev') {
                    bat 'docker build -t rect-beach-resort-deve .'
                }
            }
        }
        stage ('Run container') {
            steps {
                bat 'docker run -d --name rect-beach-resort-dev -p 3000:3000 ecommerce:latest'
            }
        }
    }
}
