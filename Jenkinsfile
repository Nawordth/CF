node{
  stage('SCM Checkout'){
    git 'https://github.com/Nawordth/CF'
  }
  

  stage("Deploy") {
                    sh "aws cloudformation create-stack --stack-name myteststack --template-body file://sampletemplate.json --parameters ParameterKey=KeyName,ParameterValue=Devops ParameterKey=SSHLocation,ParameterValue=0.0.0.0/0 ParameterKey=WebServerCount,ParameterValue=2 ParameterKey=WebServerInstanceType,ParameterValue=t2.small"
  }
}
