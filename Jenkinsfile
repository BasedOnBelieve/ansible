pipeline {
    agent {label 'ans'}

    stages {
        stage('Run Ansible Playbook') {
            steps{  
                ansiblePlaybook( credentialsId: 'ansible', installation: 'ansible', 
                inventory: '/test/roles-04/inventory/aws_ec2.yml', playbook: '/test/roles-04/playbook-role-04.yml'
            )
            }
        }
    }
}