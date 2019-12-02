# Deploying an Apache, a nodeJS server and a nodeJS Docker container as well on nodeJS server

Infra Details:
---
Host: ansible-web (Apache)

IP: 192.168.56.100

Host: ansible-nodejs (nodeJS and Docker nodeJS)

IP: 192.168.56.200

Host: ansible-controller

IP: 192.168.56.10

---
# First Usage:
  * Make exam user and set password (000000)
  ~~~
  adduser exam
  passwd exam
  ~~~
  
  * Add 'exam' user to sudoers with no password
  ~~~
  visudo
  ~~~
  append file with:
  ~~~
  exam ALL=(ALL) NOPASSWD: ALL
  ~~~
  
  * Install git on your controller
  ~~~
  yum install git -y
  ~~~
  
  * Clone this repo
  ~~~
  git clone https://github.com/gjasusa/Ansible_Docker_Exam.git
  ~~~
  
  * Install epel-release and ansible on your controller
  ~~~
  yum install epel-release -y
  yum install ansible -y
  ~~~
  
  * Change user to 'exam'
  ~~~
  su - exam
  ~~~
  
  * Make SSH keypairs with:
  ~~~
  ssh-keygen
  ~~~
  
  Push ENTER three times, it creates ssh keypair with default locations for 'exam' user
  
  * Change user back to root
  ~~~
  CTRL+D
  ~~~
  
  * Change DIR where my repo cloned and you can see the files
  ~~~
  cd /here/my/repo/was/cloned
  ~~~
    
  * First we need to create 'exam' user on remote hosts as 'root' and spread ssh key for 'exam' user on remote hosts:
  ~~~
  ansible-playbook -i create_user_hosts -k create_user.yaml
  ~~~
  
  * Change user to 'exam'
  ~~~
  su - exam
  ~~~
  
  * Run my playbook that installs Apache and nodeJS server with nodeJS Docker container on nodejs server
  ~~~
  ansible-playbook -i install_hosts install.yaml
  ~~~
  
  # Well done you have a separate Apache and nodeJS server with nodeJS Docker container on nodeJS server
  
  
  
 

  
