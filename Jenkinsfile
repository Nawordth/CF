node{
  stage('SCM Checkout'){
    git 'https://github.com/Nawordth/CF'
  }
  

  stage("Deploy") {
                    sh "export ANSIBLE_HOST_KEY_CHECKING=False"
                    sh "chmod +x ./ec2.py"
                    sh "ansible-playbook playbook1.yml -i ./ec2.py --limit 'tag_Network_Public'"
  }
}
