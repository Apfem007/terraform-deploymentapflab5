pipeline {
    agent any
    parameters {
        choice(name: 'action', choices: ['apply', 'destroy'], description: 'Terraform action to run')
    }
    stages {
        stage("terraform init") {
            steps {
                sh 'terraform init'
            }
        }

        stage("terraform Action") {
            steps {
                echo "Terraform action is --> ${params.action}"
                sh "terraform ${params.action} --auto-approve"
            }
        }
    }
}
