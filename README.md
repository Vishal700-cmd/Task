# Task

## Assignmet:
## Pre-requisite :
- OS: Base OS is Linux Mint. Server OS is RedHat Enterprise Linux 8 (RHEL8) in Virtual Box.
- In RHEL8 some of the softwares needed are Docker (also need the httpd image downloaded in it),        - Jenkins (also github plugin should be installed in it).
- In Linux Mint we need git bash software.
- At the starting stop the firewalld in RHEL8 and start the docker and jenkins services

### GIT BASH :-

 - Create a local repository in git and add files on the local System first 
 - Create a branch named "dev1" and add some content to its files and the default is master 
 - Push the hole file  in github 
 
 <img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/git%20bash.png" width ="1500" height ="500">
 
 ### JENKINS:
Job1 Task :
 - Select Git in SCM and Provide branch of "dev1"
 - Select Build Trigger as Poll SCM
 - Then type the following commands in Execute shell 
   - sudo cp  -rvf * /root/testing 
   - if sudo docker ps  | grep myos
   - then
   - echo "Already Running"
   - else 
   - sudo docker run -dit -v /root/testing:/usr/local/apache2/htdocs/ --name myos httpd 
   - fi
  
    #### Apply and Save
    
    <img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/img/jenkins%20.png" width ="1500" height ="500">
    <img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/img/2.png" width ="1500" height ="500">
    <img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/img/3.png" width ="1500" height ="500">
    <img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/img/1.png" width ="1500" height ="500">



      Job2 Task :
      - Select Git in SCM and Provide branch of "Master"
      - Select Build Trigger as Poll SCM
      - Then type the following commands in Execute shell 
       
        - sudo cp  -rvf * /root/production
        - if sudo docker ps  | grep myos1
        - then
        - echo "Already Running"
        - else 
        - sudo docker run -dit  -p 8081:80 -v /root/production:/usr/local/apache2/htdocs/ --name myos1 httpd 
        - fi 
        #### Apply and Save 
<img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/4.png" width ="1500" height ="500">
<img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/5.png" width ="1500" height ="500">
<img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/6.png" width ="1500" height ="500">
<img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/7.png" width ="1500" height ="500">

Job3 Task :
 - Type the following in Execute Shell
    - cd /work/homework/
    - sudo git fetch
    - sudo git pull
    - sudo cp -r -v -f /test   /work/homework/
    - sudo git checkout master 
    - sudo git merge dev1 
    - sudo git commit . -m "Upadated"
    - sudo git push https://YOUR_GITHUB_USER_ID:YOUR_GITHUB_PASSWORD@github.com/YOUR_USER_ID/REPOSITORY_NAME.git
 
      <img src ="https://github.com/Vishal700-cmd/Task/blob/master/img/8.png" width ="1500" height = "500">
