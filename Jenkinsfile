pipeline{
  agent any  
  stages{  
     
      stage('Git checkout') {
            steps {
                git branch: 'main', credentialsId: '', url: 'https://github.com/evarestigwe/ansible_Demo.git'
            }
        }
      stage("Run an ansible playbook"){
        steps{
          ansiblePlaybook credentialsId: 'ssh-key', inventory: 'hosts', playbook: 'nginx_install.yaml'
        }
      }
      stage("Print Nginx Installed"){
        steps{
           sh"echo nginx installed on all servers"
        }
      }
  }
}
