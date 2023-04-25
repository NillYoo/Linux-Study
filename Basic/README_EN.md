# Understanding Basic Linux Concepts

## History and Background of Linux

- Linux is an open-source operating system developed by Linus Torvalds in 1991
- Linux is based on the design principles and architecture of the Unix operating system, and it is highly regarded for its stability, scalability, and security
- As an open-source operating system, Linux allows anyone to use, modify, and distribute it freely
- Linux has continuously evolved with contributions from developers worldwide and is used in various devices and environments (servers, desktops, smartphones, etc.)
- The Linux operating system consists of a kernel and user space
- The kernel serves as the interface between hardware and applications, while user space is where applications and libraries run
- The Linux kernel provides functions such as efficient hardware management and performance optimization
- There are various Linux distributions, which are software collections that package the Linux kernel with necessary applications, libraries, and tools
- Notable distributions include Ubuntu, Fedora, Debian, and CentOS
- Each distribution offers a user-friendly interface, package management system, community support, and can be chosen based on user needs and preferences

</br>

---

</br>

## Understanding Shell and Terminal Usage

### Shell

- The shell is the `interface between the user and the operating system`, responsible for `interpreting and executing commands` entered by the user
- Various shell programs are available in Linux, including `bash` (Bourne Again Shell), `zsh` (Z Shell), and `fish` (Friendly Interactive Shell)
- `bash` is the most commonly used shell

### Terminal

- The terminal is a program that `provides an environment for entering commands and displaying results in the shell`
- Terminals can be classified into physical hardware terminals and software terminals
- In Linux, software terminal programs are used to access the shell
- Notable terminal programs include `GNOME Terminal`, `Konsole`, and `xterm`

### Prompt

- When accessing the shell through the terminal, a prompt is displayed
- The prompt indicates that the user can enter commands and typically includes information such as the username, hostname, and working directory

```
[root@localhost ~]#
```

## Frequently Used Commands

### `cd` (change directory)
- Command for `changing` directories

> For example, to move to the 'Documents' directory, you would enter the following:
```
[root@localhost ~]# cd Documents
[root@localhost Documents]#
```

### `pwd` (print working directory)
- Outputs the `path` of the current working directory
- After changing directories with the `cd` command, it is a good practice to use the `pwd` command to verify your current location
```
[root@localhost ~]# pwd
/root
```

### `ls` (list)
- `Lists` files and directories in the current directory
- Using the `-l` option displays more detailed information
- Using the `-a` option lists all files and directories, including hidden ones


```
[root@localhost ~]# ls
공개  다운로드  문서  바탕화면  비디오  사진  서식  음악

[root@localhost ~]# ls -l
합계 60
drwxr-xr-x.  2 root root 4096  3월 10 23:47 공개
drwxr-xr-x.  2 root root 4096  3월 10 23:47 다운로드
drwxr-xr-x.  2 root root 4096  3월 10 23:47 문서
drwxr-xr-x.  2 root root 4096  3월 10 23:47 바탕화면
drwxr-xr-x.  2 root root 4096  3월 10 23:47 비디오
drwxr-xr-x.  2 root root 4096  3월 10 23:47 사진
drwxr-xr-x.  2 root root 4096  3월 10 23:47 서식
drwxr-xr-x.  2 root root 4096  3월 10 23:47 음악

[root@localhost ~]# ls -al
함계 128
dr-xr-x---. 22 root root 4096  4월 20 21:50 .
dr-xr-xr-x. 18 root root 4096  3월 31 08:43 ..
-rw-------.  1 root root 1550  4월 20 21:50 .ICEauthority
-rw-------.  1 root root 3030  4월 14 22:17 .bash_history
-rw-r--r--.  1 root root   18  2월  9  2018 .bash_logout
-rw-r--r--.  1 root root  176  2월  9  2018 .bash_profile
-rw-r--r--.  1 root root  176  2월  9  2018 .bashrc
drwx------. 14 root root 4096  3월 30 23:43 .cache
drwx------. 16 root root 4096  3월 30 23:43 .config
-rw-r--r--.  1 root root  100  2월  9  2018 .cshrc
drwx------   3 root root 4096  3월 30 23:54 .dbus
-rw-------.  1 root root   16  3월 10 23:47 .esd_auth
drwx------.  3 root root 4096  3월 10 23:47 .local
drwx------.  4 root root 4096  3월 11 00:14 .mozilla
drwxr-----.  3 root root 4096  3월 10 23:47 .pki
-rw-r--r--.  1 root root  129  2월  9  2018 .tcshrc
-rw-r--r--.  1 root root  189  3월 11 00:09 .wget-hsts
-rw-------.  1 root root  952  3월 10 23:40 anaconda-ks.cfg
drwxr-xr-x.  7 root root 4096  3월 11 00:11 firefox
drwxr-xr-x.  2 root root 4096  3월 10 23:47 공개
drwxr-xr-x.  2 root root 4096  3월 10 23:47 다운로드
drwxr-xr-x.  2 root root 4096  3월 10 23:47 문서
drwxr-xr-x.  2 root root 4096  3월 10 23:47 바탕화면
drwxr-xr-x.  2 root root 4096  3월 10 23:47 비디오
drwxr-xr-x.  2 root root 4096  3월 10 23:47 사진
drwxr-xr-x.  2 root root 4096  3월 10 23:47 서식
drwxr-xr-x.  2 root root 4096  3월 10 23:47 음악
```

### `mkdir` (make directory)
- `Create` a new `directory`

> For example, to create a directory named 'example', enter the following:

```
[root@localhost ~]# mkdir example
```

### `touch`
- `Create` a new `file`

> For example, to create a file named 'test.txt', enter the following:
```
[root@localhost ~]# touch test.txt
```

### `rm` (remove)
- `Delete` files or directories
- To delete a directory, use the `-r` option

> For example, to delete the 'test.txt' file or the 'testGroup' directory, enter the following:

```
[root@localhost ~]# rm test.txt
[root@localhost ~]# rm -r testGroup
```

### `cp` (copy)
- `Copy` files or directories
- To copy a directory, use the `-r` option

> For example, to copy 'file1.txt' to 'file2.txt', enter the following:

```
[root@localhost ~]# cp file1.txt file2.txt
```

> For example, to copy 'dir1' to 'dir2', enter the following:

```
[root@localhost ~]# cp -r dir1 dir2
```

### `mv` (move)
- `Move` files or directories or `rename` them

> For example, to move 'old.txt' to the 'newDir' directory or to rename it, enter the following:

```
[root@localhost ~]# mv old.txt newDir // Move into the newDir directory
[root@localhost ~]# mv old.txt new.txt // Rename to new.txt
```

### `find`
- `Search` for files or directories

> For example, to search for 'network' in the current directory and its subdirectories, enter the following:

```
[root@localhost /]# find . -name network

./run/libvirt/network
./etc/rc.d/init.d/network
./etc/vmware-tools/scripts/vmware/network
./etc/sysconfig/network
./etc/systemd/network
./var/lib/libvirt/network
./usr/lib64/python3.6/site-packages/pyanaconda/modules/network
./usr/lib/systemd/network
```
### `grep` (global regular expression print)
- Search for lines in a file that match a `string` or `regular expression`

> For example, to search for the string 'rpm' in 'fedora.repo', enter the following:

```
[root@localhost yum.repos.d]# grep rpm fedora.repo 

type=rpm
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-$releasever-$basearch
type=rpm
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-$releasever-$basearch
type=rpm
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-fedora-$releasever-$basearch
```

### `cat` (concatenate)
- Print the contents of a file or concatenate files and print the output

> For example, to print the contents of 'helloworld.txt', enter the following:

```
[root@localhost ~]# cat helloworld.txt

hello world!!!!
Welcome linux world!!! 
happy coding!!
```

### `nano`, `gedit`, `vi`, `vim`, `emacs`, etc.
- Text editors
- Use these editors to open and edit files

> For example, to open 'testfile.txt' in the nano editor, enter the following:

```
[root@localhost ~]# nano testfile.txt
```

### `sudo` (superuser do)
- Run a command with `administrative privileges`
- Use `sudo` to perform tasks that require administrative privileges when logged in as a regular user

> For example, to install the vim package, enter the following:

```
[fedora@localhost ~]$ sudo dnf install vim
```

### `chmod` (change mode)
- Change the permissions of a file or directory
- r: read, w:write, x:execute
- rwx rwx rwx (user group other)
- To express rwx in octal, use (r:4, w:2, x:1)
- To grant all users (owner, group, and others) permission, use 777

> For example, to grant all users read, write, and execute permissions for 'test1.txt', enter the following:

```
[fedora@localhost ~]$ ls -l test1.txt
-rw-rw-r-- 1 fedora fedora 14  4월 20 23:07 test1.txt       //only Read

[fedora@localhost ~]$ chmod 777 test1.txt

[fedora@localhost ~]$ ls -l test1.txt
-rwxrwxrwx 1 fedora fedora 14  4월 20 23:07 test1.txt // All Permissions

```

### `df` (disk free)
- Check the disk space usage of a file system
- Use the `-h` option to display in a human-readable format

> For example, to check the disk space usage of the current file system in a human-readable format, enter the following:

```
[fedora@localhost ~]$ df -h

Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        973M     0  973M   0% /dev
tmpfs           985M     0  985M   0% /dev/shm
tmpfs           985M  1.6M  984M   1% /run
tmpfs           985M     0  985M   0% /sys/fs/cgroup
/dev/nvme0n1p2   75G  6.5G   65G  10% /
tmpfs           985M  112K  985M   1% /tmp
tmpfs           197M   16K  197M   1% /run/user/42
tmpfs           197M  5.7M  192M   3% /run/user/1000

```

### `du` (disk usage)
- Check the `disk usage` by `directory`
- Use the `-h` option for human-readable format

```
[fedora@localhost ~]$ du -h

4.0K	./다운로드
4.0K	./.pki/nssdb
8.0K	./.pki
4.0K	./바탕화면
4.0K	./공개
4.0K	./.cache/libgweather
4.0K	./.cache/gnome-calculator
4.0K	./.cache/yelp/WebKitCache/Version 12/Blobs
12K	./.cache/yelp/WebKitCache/Version 12
16K	./.cache/yelp/WebKitCache
20K	./.cache/yelp
8.0K	./.cache/babl
4.0K	./.cache/gegl-0.3/swap
...
```

### `ps` (process status)
- Check the currently `running processes`
- `ps -ef | grep <process name>` is commonly used
- The `-aux` option displays all processes running on the system with detailed information.

```
[fedora@localhost ~]$ ps -ef | grep bash

fedora     1861   1815  0 22:53 pts/0    00:00:00 bash
fedora    31009   1861  0 23:39 pts/0    00:00:00 grep --color=auto bash

[fedora@localhost ~]$ ps -aux

USER        PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root          1  0.0  0.4 171316  8900 ?        Ss   22:52   0:01 /usr/lib/systemd/systemd --switched-root --sys
root          2  0.0  0.0      0     0 ?        S    22:52   0:00 [kthreadd]
root          4  0.0  0.0      0     0 ?        I<   22:52   0:00 [kworker/0:0H]
root          6  0.0  0.0      0     0 ?        I<   22:52   0:00 [mm_percpu_wq]
root          7  0.0  0.0      0     0 ?        S    22:52   0:00 [ksoftirqd/0]
root          8  0.0  0.0      0     0 ?        I    22:52   0:00 [rcu_sched]
root          9  0.0  0.0      0     0 ?        I    22:52   0:00 [rcu_bh]
root         10  0.0  0.0      0     0 ?        S    22:52   0:00 [migration/0]
...
```

### `kill` 
- Terminates a process
- Specific processes can be terminated using the Process ID (PID)
- The `-9` option can be used for forceful termination

> For example, to terminate the process with PID 2054, type the following command:


```
[fedora@localhost ~]$ kill 2054
```

### `pstree`
- Shows the parent-child relationship of processes in a tree-like format.
```
[fedora@localhost ~]$ pstree

systemd─┬─ModemManager───2*[{ModemManager}]
        ├─NetworkManager───2*[{NetworkManager}]
        ├─VGAuthService
        ├─abrt-dbus───2*[{abrt-dbus}]
        ├─3*[abrt-dump-journ]
        ├─abrtd───2*[{abrtd}]
        ...
```

### `wget`
- Download files from the web.

> For example, if the URL of the file is 'https://linux.com/test.zip', you can download it using the following command:

```
[fedora@localhost ~]$ wget https://linux.com/test.zip
```

### `curl`
- Command used for sending or receiving data from the web or calling APIs.

> For example, to output the HTML source of a web page, type the following command:

```
[fedora@localhost ~]$ curl google.com

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="http://www.google.com/">here</A>.
</BODY></HTML>

```

### `tar`
- `Compress` or `extract` files or directories
- Actions: c (Compress), x (extract), t (check path)
- Options: f (file, *required option), v (view course), J (tar+xz), z (tar+gzip), j (tar+bzip2)
- Compress files using `xz` format
```
[fedora@localhost ~]$ tar cvfJ mytest.tar.xz testzip2
testzip2

[fedora@localhost ~]$ ls
mytest.tar.xz  test  testzip  testzip2 

```
- extract files using `xz` format
```
[fedora@localhost ~]$ ls
mytest.tar.xz  test  testzip

[fedora@localhost ~]$ tar xvfJ mytest.tar.xz
testzip2

[fedora@localhost ~]$ ls
mytest.tar.xz  test  testzip  testzip2
```