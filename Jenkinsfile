pipeline{
  parameters{
     boolean{name: 'Terraform_Init', defaultValue: '', description: 'Initialize the terraform configuration'}
     boolean{name: 'Terraform_Plan', defaultValue: '', description: 'Plan the terraform configuration'}
     boolean{name: 'Terraform_Apply', defaultValue: '', description: 'Apply the terraform configuration'}
     boolean{name: 'Terraform_Destroy', defaultValue: '', description: 'Destroy the terraform configuration'}
  }
  agent any
  stages{
    stage(Checkout){
       steps {
                git branch: 'master', credentialsId: 'terraform-login-private-key', url: 'https://github.com/RishwanaBegam/test.git'
            }
    }
    stage(Terraform Initialization){
      when {
        params.Terraform_Action
      }
      steps{
        sh 'terraform init' 
      }
    }
    stage(Terraform Plan){
      steps{
        sh 'terraform plan'
      }
    }
    stage(Terraform apply){
      steps{
        sh 'terraform apply'
      }
    }
    stage(Terraform destroy){
      steps{
        sh 'terraform destroy'
      }
    }
}
}
