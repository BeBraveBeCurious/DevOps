

# Assignment



Problem Statement: 

1.Create a directory name it Docker-Folder and a file name Dockerfile, Create 5 users and a group, name the group "CodingDojo" and add these new users to the group "CodingDojo" **Only allow users in this group to access Docker-Folder**



```bash
(base) root@e5866a79485e:/# mkdir Docker-Folder
(base) root@e5866a79485e:/# cd Docker-Folder/
(base) root@e5866a79485e:/Docker-Folder# touch Dockerfile 
(base) root@e5866a79485e:/Docker-Folder# sudo useradd user1
(base) root@e5866a79485e:/Docker-Folder# sudo useradd user2
(base) root@e5866a79485e:/Docker-Folder# sudo useradd user3
(base) root@e5866a79485e:/Docker-Folder# sudo useradd user4
(base) root@e5866a79485e:/Docker-Folder# sudo useradd user5
(base) root@e5866a79485e:/Docker-Folder# sudo groupadd CodingDojo
groupadd: group 'CodingDojo' already exists
(base) root@e5866a79485e:/Docker-Folder# sudo groupdel CodingDojo
(base) root@e5866a79485e:/Docker-Folder# sudo groupadd CodingDojo
(base) root@e5866a79485e:/Docker-Folder# sudo usermod -a -G CodingDojo user1
(base) root@e5866a79485e:/Docker-Folder# sudo usermod -a -G CodingDojo user2
(base) root@e5866a79485e:/Docker-Folder# sudo usermod -a -G CodingDojo user3
(base) root@e5866a79485e:/Docker-Folder# sudo usermod -a -G CodingDojo user4
(base) root@e5866a79485e:/Docker-Folder# sudo usermod -a -G CodingDojo user5
(base) root@e5866a79485e:/Docker-Folder# ls
Dockerfile
(base) root@e5866a79485e:/Docker-Folder# cd ..            
(base) root@e5866a79485e:/# chgrp CodingDojo Docker-Folder/
(base) root@e5866a79485e:/# grep CodingDojo /etc/group
CodingDojo:x:1020:user1,user2,user3,user4,user5
(base) root@e5866a79485e:/# whoami
root
```











2.You are hosting a system network where you have two processes running in the background. First one is a process to monitor the uptime of each system and second one is a process that keeps track of all processes running in the working environment. The priority value of the first process is 8. The priority value of the second process is lower than the first process. Use 'renice' to change the priority.



```bash
sudo renice -n 8 -p 3427
```







3. Create a cron job that will run two times in an hour and this job should repeat every hour.



```powershell
(base) root@e5866a79485e:/# crontab -e
*/30 0-23 * * * uptime >> ~/cron.txt 2>&1
0,30 * * * * /home/${USER}/test.py
(base) root@e5866a79485e:/# crontab -l
```

![image-20211231154202963](https://s2.loli.net/2021/12/31/xEMmdDPkuOCe3Jj.png)



4.You work for CodingDojo. Your job is to manage Linux-based Servers. And you have been asked to: Add a website with it's IP address in the etc/hosts file. Ping to see if it's working. Connect to that server using ftp and transfer a file from your pc to that server. Install a web server and allow access to the port number of that server.



```bash
sudo systemclt start httpd
sudo systemclt status httpd

```

5.Write a shell script to look for a file name Dockerfile if it doesn't exist create a new file per the requirement.



```bash
#!/bin/sh
check_file_exist=$(ls |grep -i Dockerfile | wc -l)
if ((check_file_exist==0));then
	echo "Dockerfile does not exists"
	# read -p "Would you like to create a new Dockerfile (y/n)?" input
	# if [[$input == 'y' || $input == 'Y']]; then
	touch Dockerfile
	echo "Dockerfile has been created successfully"
	# fi
fi
```

![image-20211231162133602](https://s2.loli.net/2021/12/31/sVA5lEhe6RyFZfx.png)



![image-20211231162200327](https://s2.loli.net/2021/12/31/jY4UTQxayvJuZrC.png)

```bash
#!/bin/sh

Filename=Dockerfile
if [ -f "$Filename"]; then
	echo "$Filename exists"
else
	touch $Filename
	echo "Dockerfile has been created successfully"
fi
```

