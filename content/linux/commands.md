---
title: "Linux命令"
date: 2017-09-24 23:16
---

[TOC]

# Linux命令
### 基本命令
#### 1. ls

   ```shell
   SYNOPSIS
        ls [-ABCFGHLOPRSTUW@abcdefghiklmnopqrstuwx1] [file ...]
   ```

   | 选                 项 | 作用                                                         |
   | ---- | ------------------------------------------------------------ |
   |   -a   | Include directory entries whose names begin with a dot (.).  |
   |   -d   | Directories are listed as plain files (not searched recursively). |
   |   -l   | List in long format.                                         |
   |   -t   | Sort by time modified.                                       |
   |   -S   | Sort files by size.                                          |
   |   -T   | used with the -l option, display complete time information for the file, including month, day, hour, minute, second, and year. |
   |   -r   | Reverse the order of the sort to get reverse lexicographical order or the oldest entries first (or largest files last, if combined with sort by size. |

   
##### 示例

```shell
# 列出所有非隐藏文件
ls
ls filename
# 列出所有文件
ls -a
# 列出所有文件及详情
ls -al
# 按照时间修改顺序列出文件
ls -lt
# 只列出目录
ls -b */
```

#### 3. cd

#### 4. mv

#### 5. cp

#### 6. mkdir

#### 7. rmdir

#### 8. rm

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

#### 9. touch

#### 10. grep

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

#### 11. find

#### 12. chmod

#### 13. chown

#### 14. awk

#### 15. xargs

### 进程
#### 1. ps -- process status

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
#### 1. netstat
	- -a
	- -n
	- -p: list pid
#### 2. iptables
	显示防火墙配置：`cat /etc/sysconfig/iptables`
	关闭防火墙：`sudo service iptables stop`
#### 3. route
	查看路由配置：`route -n`
#### 4. scp
	文件远程传输

### 系统状态
#### 1. ls /proc/<pid\>/cwd
#### 2. ls /proc/meminfo
#### 3. ls /proc/cpuinfo
#### 4. lsblk
#### 5. df
#### 6. lvm
#### 7. lvs
#### 8. top

### 压缩、解压
#### 1. tar
	注意：c/x/t选项不能同时使用，f选项接文档名，后面不能再加其他选项
	- -c 压缩
	- -z 是否具有 gzip 属性
	- -t 查看 tarfile 里面的文件！
	- -x 解压
	- -v 压缩的过程中显示文件
	- -f 使用档名
#### 2. zip
#### 3. unzip
	- -d <exdir\>
	- -q quiet mode