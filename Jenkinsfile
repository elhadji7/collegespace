pipeline {
    agent any
    
    stages {
        stage('Récupération du code') {
            steps {
                git branch: 'master',
                url: 'https://github.com/elhadji7/collegespace.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'composer install'
            }
        }    
        stage('Package Application') {
            steps {
                sh 'zip -r college.zip .'
            }
        } 
        stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook /home/user/ansible/phpdeployment.yml'
            }
        }
    }
}  
