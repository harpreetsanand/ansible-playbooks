pipeline {
  agent none
  stages {
    stage('VM Creation ') {
      steps {
        sh '/usr/local/bin/terrafrom -version '
      }
    }
    stage('Ansible User Creation ') {
      steps {
        sh '''cd /root/playbooks/

ansible-playbook -i inventory.ini user_add.yml'''
      }
    }
    stage('Setup Docker ') {
      steps {
        sh '''cd /root/playbooks
ansible-playbook -i inventory.ini docker.yml'''
      }
    }
  }
  environment {
    env = 'dev'
  }
}