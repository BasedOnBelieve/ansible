pipeline {
    agent none

    stages {
        stage('Clone Code') {
            agent { label 'build' }
            steps {
                git branch: 'master', url: 'https://github.com/BasedOnBelieve/ecomm-3.git'
            }
        }

        stage('Run Ansible Playbook') {
            agent { label 'ansible' }
            steps {
                ansiblePlaybook(
                    ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, inventory: 
                    '/home/ec2-user/ansible/others/hosts.ini', playbook: '/home/ec2-user/ansible/03-role-playbook.yml'
            }
        }
    }
}