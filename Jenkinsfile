pipeline {

    agent any

    stages {

        stage('Checkout') {

            steps {
                git 'https://github.com/deep-snaatak/ansible-playbook-ci.git'
            }
        }

        stage('Syntax Check') {

            steps {
                sh 'ansible-playbook --syntax-check -i inventory playbook.yml'
            }
        }

        stage('Ansible Lint') {

            steps {
                sh 'ansible-lint playbook.yml'
            }
        }

        stage('Dry Run Validation') {

            steps {
                sh 'ansible-playbook -i inventory playbook.yml --check'
            }
        }
    }
}
