pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/MuhammadHaafiz/deployment-ci-cd'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    apt-get update
                    apt-get install -y ansible
                '''
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh '''
                    ansible-playbook -i inventory.ini playbook.yml
                '''
            }
        }
    }
}
