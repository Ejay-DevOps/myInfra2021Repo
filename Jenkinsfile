pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
            checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'fc9bdb0d-f042-45d7-9528-637bb29acedd', url: 'https://github.com/Ejay-DevOps/myInfra2021Repo']])
            }
        }
        
        stage ("terraform init") {
            steps {
                sh ('terraform init -reconfigure') 
            }
        }
        stage ("terraform plan") {
            steps {
                sh ('terraform plan') 
            }
        }
                
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
