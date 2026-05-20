pipeline {

    agent any

    stages {

        stage('Syntax Check') {

            steps {
                sh 'ansible-playbook --syntax-check -i inventory playbook.yaml'
            }
        }

        stage('Ansible Lint') {

            steps {
                sh 'ansible-lint playbook.yaml'
            }
        }

        stage('Dry Run Validation') {

            steps {
                sh 'ansible-playbook -i inventory playbook.yaml --check'
            }
        }
    }
}
