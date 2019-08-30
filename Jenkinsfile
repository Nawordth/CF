node{
  stage('SCM Checkout'){
    git 'https://github.com/Nawordth/CF'
  }
  

  stage("Deploy") {
    sh "export AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}"
    sh "export AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}"
    sh "export AWS_DEFAULT_REGION=${AWS_REGION}"
    
                    sh "sudo aws cloudformation create-stack --stack-name myteststack --template-body file://VPC_AutoScaling_With_Public_IPs4.txt --parameters ParameterKey=KeyName,ParameterValue=Devops ParameterKey=SSHLocation,ParameterValue=0.0.0.0/0 ParameterKey=WebServerCount,ParameterValue=2 ParameterKey=WebServerInstanceType,ParameterValue=t2.small"
  }
}
