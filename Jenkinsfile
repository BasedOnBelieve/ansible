pipeline {
    agent {label 'ansible'}

    stages {
        stage('Run Ansible Playbook') {
            steps{  
                ansiblePlaybook( credentialsId: 'ansible', installation: 'ansible', 
                inventory: '/ansible/roles-4/inventory/aws_ec2.yml', playbook: '/ansible/roles-4/playbook-role-04.yml'
            )
            }
        }
    }
}