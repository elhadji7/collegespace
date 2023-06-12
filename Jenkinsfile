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
        stage('Package Application') {
            steps {
                sh 'zip -r college.zip .'
            }
        } 
        stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook /home/user/ansible/phpdeployment.yml --start-at-task="Unzip application package"'
            }
        }
    }
}
