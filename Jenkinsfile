pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID     = credentials('aws-credential')
        AWS_SECRET_ACCESS_KEY = credentials('aws-credential')
    }
    stages {
        // stage('Checkout') {
        //     steps {
        //         git 'https://github.com/vinceinstructor/terraform-project.git'
        //     }
        // }
        // stage('Terraform install') {
        //     steps {
        //         sh 'snap install terraform --classic'
        //     }
        // }
        // stage('Terraform Init') {
        //     steps {
        //         sh 'cd git-cicd && terraform init'
        //     }
        // }
        stage('cd git-cicd &&  Terraform Plan') {
            steps {
                sh 'terraform plan '
            }
        }
        stage('cd git-cicd &&  Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}