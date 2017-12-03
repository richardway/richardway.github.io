---
title: "Linux命令"
date: 2017-09-24 23:16
---

[TOC]

# Linux命令
### 基本命令
1. ls
2. cd
3. mv
4. cp
5. mkdir
6. rmdir
7. rm

	```
	 SYNOPSIS
     rm [-dfiPRrvW] file ...
     unlink file
	```

	|选项|作用|
	|:---|--|
	|__-d__|Attempt to remove directories as well as other types of files.|
	|__-f__|Forcely remove without asking.|
	|__-r__|Attempt to remove the file hierarchy rooted in each file argument.|

8. touch
9. grep

	```
	 SYNOPSIS
     grep [-abcdDEFGHhIiJLlmnOopqRSsUVvwxZ] [-A num] [-B num] [-C[num]]
          [-e pattern] [-f file] [--binary-files=value] [--color[=when]]
          [--colour[=when]] [--context[=num]] [--label] [--line-buffered]
          [--null] [pattern] [file ...]
	```

	|选项|作用|
	|:---|--|
	|__-v__|Selected lines are those __not__ matching any of the specified patterns.|
	|__-i__|Perform case insensitive matching.|
	|__-r__|Recursively search subdirectories listed.|

10. find
11. chmod
12. chown
13. awk
14. xargs

### 进程
1. ps -- process status

	```
	 SYNOPSIS
	 ps [-AaCcEefhjlMmrSTvwXx] [-O fmt | -o fmt] [-G gid[,gid...]]
		[-g grp[,grp...]] [-u uid[,uid...]] [-p pid[,pid...]] [-t tty[,tty...]]
		[-U user[,user...]]
	 ps [-L]
	```

	|选项|作用|
	|:---|--|
	|__-e__|Select all processes, identical to __-A__|
	|__-f__|Display the uid, pid, parent pid, recent CPU usage, process start time, controlling tty, elapsed CPU usage, and the associated command.If the __-u__ option is also used, display the user name rather then the numeric uid.  When __-o__ or __-O__ is used to add to the display following __-f__, the command field is not truncated as severely as it is in other formats.|
	|__-a__|Display information about other users' processes as well as your own.  This will skip any processes which do not have a controlling terminal, unless the __-x__ option is also specified.|
	|__-u__|Display the processes belonging to the specified usernames.|
	|__-x__|When displaying processes matched by other options, include processes which do not have a controlling terminal.|
	|__-X__|When displaying processes matched by other options, skip any processes which do not have a controlling terminal.|

### 网络
1. netstat
	- -a
	- -n
	- -p: list pid
2. iptables
	显示防火墙配置：`cat /etc/sysconfig/iptables`
	关闭防火墙：`sudo service iptables stop`
3. route
	查看路由配置：`route -n`
4. scp
	文件远程传输

### 系统状态
1. ls /proc/<pid\>/cwd
2. ls /proc/meminfo
3. ls /proc/cpuinfo
4. lsblk
5. df
6. lvm
7. lvs
8. top

### 压缩、解压
1. tar
2. zip
3. unzip
	- -d <exdir\>