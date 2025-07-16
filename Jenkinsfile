pipeline {
    agent none

    stages {
        stage('Clone Code') {
            agent { label 'build' } // This runs on Jenkins build node
            steps {
                git branch: 'main', url: 'https://github.com/BasedOnBelieve/food3.git'
            }
        }

        stage('Run Ansible Playbook') {
            agent { label 'ansible' } // This runs on the Ansible server
            steps {
                sh '''
                    
                    cd /ansible/
                    ansible-playbook -i others/hosts.ini 03-role-playbook.yml
                '''
            }
        }
    }
}
