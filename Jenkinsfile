pipeline {
    agent any
    
    stages {
        stage('Clone Git Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Meenakshi0812/different-servers.git'
            }
        }
        
        stage('Copy Files') {
            steps {
                sshagent(['jenkins-private-ssh-key']) {
                    sh 'scp -r /home/ec2-user ubuntu@3.80.125.254:/var/www/html'
                }
            }
        }
    }
}
