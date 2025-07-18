pipeline {
    agent none

    stages {
        stage('Clone Code') {
            agent { 'build' }
            steps {
                git branch: 'master', url: 'https://github.com/BasedOnBelieve/ecomm-3.git'
            }
        }

        stage('Run Ansible Playbook') {
            agent { label 'ansible' }
            steps {
                ansiblePlaybook(
                    credentialsId: 'ansible', disableHostKeyChecking: true, inventory: 
                    '/others/hosts.ini', playbook: '03-role-playbook.yml'
                )
            }
        }
    }
}