pipeline {
    agent any

    environment {
        ANSIBLE_HOST = '192.168.0.110'
        ANSIBLE_USER = 'champ'
        ANSIBLE_PLAYBOOK = '/home/champ/ansible/router_playbook_template.yml'
    }

    stages {
        stage('Run Ansible Playbook') {
            steps {
                sshagent(['ssh-agent-ansible-192.168.0.110']) {
                    sh """
                    ssh -o StrictHostKeyChecking=no ${ANSIBLE_USER}@${ANSIBLE_HOST} \\
                    'ansible-playbook ${ANSIBLE_PLAYBOOK}'
                    """
                }
            }
        }
    }
}



