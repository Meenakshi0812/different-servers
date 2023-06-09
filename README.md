## how to trasfer files from one server to another server using jenkins pipeline
- consider 2 servers. 1.jenkins server 2.application server
- in jenkins server i'm having my required files and i want to copy those files to application server /var/www/html path
- in application server i installed apache
## requirements:
- jenkins installed and running
- jenkins public key(id_rsa.pub) needs to copy and paste in application server's authorized_keys file
- SSH Agent plugin needs to download
- provide ssh credentials in the kind ssh user name and private key . copy the private key of application server(id_rsa) in jenkins credentials . remaining details like  id and name of ur choice.
- use scp command to transfer files from one server to another server
#### note:
id_rsa       ->private key -> used for authentication
id_rsa.pub   ->public key  -> used for ssh connection

## how to install jenkins on amazon linux
- sudo yum update –y
- sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
- sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
- sudo yum upgrade
- sudo dnf install java-11-amazon-corretto -y
- sudo yum install jenkins -y
- sudo systemctl enable jenkins
- sudo systemctl start jenkins
-  sudo systemctl status jenkins
