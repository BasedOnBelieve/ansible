pipeline {
    agent { label 'deploy' }

    stages {
        stage( 'Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Ansible Playbook') {
            steps{  
                ansiblePlaybook( credentialsId: 'ansible', installation: 'ansible', 
                inventory: '/roles-04/inventory/aws_ec2.yml', playbook: '/webapp/roles-04/playbook-role-04.yml'
            )
            }
        }

    }
}