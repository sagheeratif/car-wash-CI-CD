pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = "false"
    }

    stages {
        stage('Run Ansible') {
            steps {
                echo 'Ansible Playing....'
                sh '''
                ansible-playbook -i localhost, -c local deploy.yml --become
                '''
            }
        }
    }

    post {
        failure {
            echo 'Deployment Failed.'
        }
        success {
            echo 'Deployment Successful.'
        }
    }
}
