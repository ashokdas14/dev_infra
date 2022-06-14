pipeline {
    agent any
	tools {
            terraform 'terraform'
        }
    stages {
	stage('Git Checkout'){
            steps{
            git branch: 'main', url: 'https://github.com/ashokdas14/dev_infra.git'
            }
        }
		
	stage('Terraform'){
            steps{
            sh 'terraform init'
	        sh 'terraform plan'
	        sh 'terraform validate'
            }
        }
	stage('Terraform Approval'){
            steps{
            input "Deploy Infra?"
            }
        }
    stage('Terraform Apply'){
            steps{
            sh 'terraform apply --auto-approve';
            }
        }
    }
}
