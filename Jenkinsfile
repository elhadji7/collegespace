pipeline {
    agent any
    
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/elhadji7/collegespace.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'composer install'
            }
        }
        
        stage('Run Unit Tests') {
            steps {
                sh 'phpunit'
            }
        }
        
        stage('Package Application') {
            steps {
                sh 'zip -r application.zip .'
            }
        }
    }
}
