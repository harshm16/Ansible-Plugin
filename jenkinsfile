pipeline {
    agent none
    stages {
        stage('Git pull'){
            agent{label 'master'}
            steps{
            //sh 'mkdir /var/lib/jenkins/workspace/ansibleplugin'
            sh 'su - root << EOF root git clone https://github.com/harshm16/Ansible-Plugin.git EOF'
                }
            }   
        stage('File creation'){
            agent{label 'master'}
            steps{
                ansiblePlaybook (credentialsId: '7e83e79f-c974-4de1-b4a1-ef454c987324', 
                inventory: '/var/lib/jenkins/workspace/ansibleplugin/hosts',
                playbook: '/var/lib/jenkins/workspace/ansibleplugin/aplugin.yml')
            }
        }
    }
}
