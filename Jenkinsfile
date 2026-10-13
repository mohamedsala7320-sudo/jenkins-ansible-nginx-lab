pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook -i inventory.ini playbook.yml'
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully.'
            echo 'Nginx installed and running successfully.'
        }
        failure {
            echo 'Pipeline failed during execution.'
            echo 'Please check the console output for errors.'
        }
        always {
            echo 'Pipeline execution completed.'
        }
    }
}