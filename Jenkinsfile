node{
  stage('SCM Checkout'){
    git 'https://github.com/Nawordth/CF'
  }
  

  stage("Deploy") {
    sh "sudo aws configure set aws_access_key_id ${AWS_ACCESS_KEY_ID}"
    sh "sudo aws configure set aws_secret_access_key ${AWS_SECRET_ACCESS_KEY}"
    sh "sudo aws configure set default.region ${AWS_REGION}"
    if ( "${OPTION}" == 'delete-stack') {
    sh "sudo aws cloudformation delete-stack --stack-name myteststack"
    }
    else {
    sh "sudo aws cloudformation ${OPTION} --stack-name myteststack --template-body file://VPC_AutoScaling_With_Public_IPs4.txt --parameters ParameterKey=KeyName,ParameterValue=devops ParameterKey=SSHLocation,ParameterValue=0.0.0.0/0 ParameterKey=WebServerCount,ParameterValue=${SERVER_COUNT} ParameterKey=WebServerInstanceType,ParameterValue=t2.small"
    sh "sudo aws cloudformation wait stack-create-complete --stack-name myteststack"
    sh "sudo aws cloudformation describe-stacks --stack-name myteststack --query "Stacks[0].Outputs[0].OutputValue" --output text"
    }
    }
}
