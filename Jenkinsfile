pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'master', url: 'https://github.com/BasedOnBelieve/ecomm-3.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                    ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, inventory: 
                    '/home/ec2-user/ansible/others/hosts.ini', playbook: '/home/ec2-user/ansible/03-role-playbook.yml'
            }
        }
    }
}