# Deploying an Apache, a nodeJS server and a nodeJS Docker container as well on nodeJS server

Infra Details:
---
Host: ansible-web (Apache)

IP: 192.168.56.100

Host: ansible-nodejs (nodeJS and Docker nodeJS)

IP: 192.168.56.200

Host: ansible-controller

IP: 192.16.56.10

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

  
