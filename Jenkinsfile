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
        stage('Copy Package') {
            steps {
                sh 'cp application.zip /home/user/ansiblena'
            }
        }
        
        stage('Run Ansible Playbook') {
            steps {
                ansible-playbook /home/user/ansible/phpdeployment.yml
            }
        }
    }
}
