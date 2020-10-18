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
| __-a__  | 包含目录下隐藏文件（以.开头）|
| __-d__   | Directories are listed as plain files (not searched recursively). |
| __-l__   | 按长格式输出 |
| __-t__   | 按修改时间降序排序 |
| __-S__   | 按文件大小降序排序 |
| __-T__   | 与 __-l__ 选项一起使用时，展示完整的时间信息 |
| __-r__   | 逆转排序结果 |


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
|__-d__|删除目录|
|__-f__|无需确认，强制删除|
|__-r__|删除指定目录下所有文件和目录|

##### 示例

```shell
# 删除文件
rm file
# 删除空目录
rm -d dir
# 删除非空目录
rm -rd dir
# 删除目录下所有内容
rm -rf dir
```

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
|__-v__| 搜索**不**符合指定条件的行 |
|__-i__| 搜索**不**区分大小写 |
|__-r__| 递归搜索子目录 |

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
|__-e__|选择所有进程，和 __-A__ 作用相同|
|__-f__|展示uid, pid, 父pid, 近期CPU使用率, 进程启动时间, 控制tty, 占用CPU时间, 启动命令|
|__-a__|展示自己的和其他用户的所有进程，跳过没有控制终端的进程|
|__-u__|展示属于指定用户的进程|
|__-x__|通过其他选项展示进程时，包含没有控制终端的进程|
|__-X__|通过其他选项展示进程时，跳过没有控制终端的进程|


##### 示例
```shell
ps -urichard -ef
```

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