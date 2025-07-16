pipeline {
    agent none

    stages {
        stage('Clone Code') {
            agent { label 'build' } // This runs on Jenkins build node
            steps {
                git branch: 'master', url: 'https://github.com/BasedOnBelieve/ecomm-3.git'
            }
        }

        stage('Run Ansible Playbook') {
            agent { label 'ansible' } // This runs on the Ansible server
            steps {
                sh '''
                    cd ansible/

                    ansible-playbook -i others/hosts.ini 03-role-playbook.yml
                '''
            }
        }
    }
}
