node{
  stage('SCM Checkout'){
    git 'https://github.com/Nawordth/CF'
  }
  

  stage("Deploy") {
                    sh "aws cloudformation create-stack --stack-name myteststack --template-body file://sampletemplate.json --parameters ParameterKey=KeyPairName,ParameterValue=Devops ParameterKey=SubnetIDs,ParameterValue=SubnetID1\\,SubnetID2"
  }
}
