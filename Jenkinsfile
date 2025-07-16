pipeline {
    agent { label 'build' }

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/BasedOnBelieve/food3.git'
            }
        }
        stage('Run Ansible Playbook') {
            agent { label 'ansible' }
            steps {
                sh '''
                    cd ansible
                    ansible-playbook -i /others/hosts.ini 03-role-playbook.yml
                '''
            }
        }
    }
}
