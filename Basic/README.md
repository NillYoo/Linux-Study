# 리눅스 기초 개념 이해

## 리눅스의 역사와 배경

- 리눅스는 1991년에 리누스 토르발스(Linus Torvalds)가 개발한 오픈소스 운영 체제
- 리눅스는 유닉스(Unix) 운영 체제의 설계 원칙과 구조를 기반으로 하며, 그 안정성과 확장성, 보안성 등이 높은 평가를 받고 있음
- 리눅스는 오픈소스 운영 체제로서 누구나 사용하고, 수정하고, 배포할 수 있는 자유를 가지고 있음
- 리눅스는 전 세계의 개발자들의 기여를 받아 지속적으로 발전해왔으며, 다양한 기기와 환경에서 사용되고 있음 (서버, 데스크톱, 스마트폰 등)
- 리눅스 운영 체제는 커널(Kernel)과 사용자 공간(User Space)으로 구성되어 있음 
- 커널은 하드웨어와 응용 프로그램 사이의 인터페이스 역할을 담당하며, 사용자 공간에서는 응용 프로그램과 라이브러리가 실행 됨
- 리눅스 커널은 하드웨어를 효율적으로 관리하고, 성능을 최적화하는 등의 기능을 제공
- 리눅스에는 다양한 배포판(Distribution)이 존재하며, 배포판은 리눅스 커널과 필요한 응용 프로그램, 라이브러리, 도구 등을 패키징하여 제공하는 소프트웨어 모음
- 대표적인 배포판으로는 Ubuntu, Fedora, Debian, CentOS 등이 있음 
- 각 배포판은 사용자 친화적인 인터페이스, 패키지 관리 시스템, 커뮤니티 지원 등을 제공하며, 사용자의 필요와 취향에 따라 선택할 수 있음

</br>

---

</br>

## 쉘과 터미널 사용법 이해

### 쉘(`Shell`)
- 쉘(Shell)은 `사용자와 운영 체제 사이의 인터페이스`로, 사용자가 `입력한 명령어를 해석하고 실행`하는 역할
- 리눅스에서는 다양한 쉘 프로그램이 있으며, 대표적으로 `bash`(Bourne Again Shell), `zsh`(Z Shell), `fish`(Friendly Interactive Shell) 등이 있음
- `bash`는 가장 일반적으로 사용되는 쉘(Shell)

### 터미널(`Terminal`)
- 터미널(Terminal)은 `쉘에 명령어를 입력하고 결과를 출력하는 환경을 제공`하는 프로그램
- 터미널은 물리적인 하드웨어 터미널과 소프트웨어 터미널로 구분할 수 있음
- 리눅스에서는 소프트웨어 터미널 프로그램을 사용하여 쉘에 접근할 수 있음 
- 대표적인 터미널 프로그램으로는 `GNOME Terminal`, `Konsole`, `xterm`

### 프롬프트(`prompt`)
- 터미널을 통해 쉘에 접속하면, 프롬프트(prompt)가 표시 됨 
- 프롬프트는 사용자가 명령어를 입력할 수 있는 상태임을 나타내며, 일반적으로 사용자 이름, 호스트 이름, 작업 디렉터리 등의 정보를 포함

```
[root@localhost ~]#
```


## 자주 사용되는 명령어

### `cd` (change directory)
 - 디렉터리 `이동` 명령어 

> 예를 들어, 'Documents' 디렉터리로 이동하려면 다음과 같이 입력해야함

```
[root@localhost ~]# cd Documents
[root@localhost Documents]#
```

### `pwd` (print working directory)
- 현재 작업중인 디렉터리의 `경로`를 출력
- `cd` 명령어를 통해 디렉터리를 이동한 후 `pwd`명령어를 통해 현재 위치를 확인 하는 것이 좋음
```
[root@localhost ~]# pwd
/root
```

### `ls` (list)
- 현재 디렉터리의 파일과 디렉터리를 `나열`
-  `-l` 옵션을 사용하면 자세한 정보를 확인할 수 있음 
-  `-a` 옵션을 사용하면 숨김 파일을 포함한 모든 파일과 디렉터리를 나열

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
- 새로운 `디렉터리`를 `생성` 

> 예를 들어, 'example'이라는 이름의 디렉터리를 생성하려면 다음과 같이 입력

```
[root@localhost ~]# mkdir example
```

### `touch` 
- 새로운 `파일`을 `생성`
  
> 예를 들어, 'test.txt'라는 이름의 파일을 생성하려면 다음과 같이 입력

```
[root@localhost ~]# touch test.txt
```

### `rm` (remove)
- 파일이나 디렉터리를 `삭제`
- 디렉터리를 삭제하려면 `-r` 옵션을 사용해야함 

> 예를 들어, 'test.txt' 파일 또는 'testGroup' 디렉터리를 삭제하려면 다음과 같이 입력

```
[root@localhost ~]# rm test.txt
[root@localhost ~]# rm -r testGroup
```

### `cp` (copy)
- 파일이나 디렉터리를 `복사`
- 디렉터리를 복사하려면 `-r` 옵션을 사용

> 예를 들어, 'file1.txt'를 'file2.txt'로 복사하려면 다음과 같이 입력

```
[root@localhost ~]# cp file1.txt file2.txt
```

> 예를 들어, 'dir1'를 'dir2'로 복사하려면 다음과 같이 입력

```
[root@localhost ~]# cp -r dir1 dir2
```

### `mv` (move)
- 파일이나 디렉터리를 `이동`하거나 `이름을 변경` 

> 예를 들어, 'old.txt'를 'newDir'디렉터리로 이동하거나 이름을 변경하려면 다음과 같이 입력

```
[root@localhost ~]# mv old.txt newDir   //newDir 디렉터리안으로 이동
[root@localhost ~]# mv old.txt new.txt    //new.txt로 이름 변경
```

### `find`
- 파일이나 디렉터리를 `검색` 

> 예를 들어, 현재 디렉터리와 하위 디렉터리에서 'network'를 찾으려면 다음과 같이 입력

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
- 파일에서 `문자열`이나 `정규 표현식`과 일치하는 줄을 `검색` 

> 예를 들어, 'fedora.repo'에서 'rpm'이라는 문자열을 찾으려면 다음과 같이 입력

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
 - 파일의 내용을 출력하거나 파일을 연결하여 출력

> 예를 들어, 'helloworld.txt'의 내용을 출력하려면 다음과 같이 입력

```
[root@localhost ~]# cat helloworld.txt

hello world!!!!
Welcome linux world!!! 
happy coding!!
```

### `nano`, `gedit`, `vi`, `vim`, `emacs` 등
- 텍스트 에디터 
- 이 에디터들을 사용하여 파일을 열고 편집할 수 있음 

> 예를 들어, 'testfile.txt'를 nano 편집기로 열려면 다음과 같이 입력

```
[root@localhost ~]# nano testfile.txt
```

### `sudo` (superuser do)
- `관리자 권한`으로 명령어를 `실행` 
- 일반 사용자로 로그인한 상태에서 관리자 권한이 필요한 작업을 수행하려면 `sudo`를 사용 

> 예를 들어, vim패키지를 설치하려면 다음과 같이 입력

```
[fedora@localhost ~]$ sudo dnf install vim
```

### `chmod` (change mode)
- 파일이나 디렉터리의 권한을 변경 
- r: read, w:write, x:execute
- rwx rwx rwx (user group other)
- rwx를 8진수로 표현하면 (r:4, w:2, x:1)
- 소유자와 그룹, 그외 사용자에게 모두 권한을 부여하는 경우 777을 입력하면 됨

> 예를 들어, 'test1.txt'에 대한 모든 사용자의 읽기, 쓰기, 실행 권한을 부여하려면 다음과 같이 입력

```
[fedora@localhost ~]$ ls -l test1.txt
-rw-rw-r-- 1 fedora fedora 14  4월 20 23:07 test1.txt       //읽기 권한 밖에 없음

[fedora@localhost ~]$ chmod 777 test1.txt

[fedora@localhost ~]$ ls -l test1.txt
-rwxrwxrwx 1 fedora fedora 14  4월 20 23:07 test1.txt //모든 권한 부여됨

```

### `df` (disk free)
- `파일 시스템`의 `디스크 공간 사용량`을 확인 
- `-h` 옵션을 사용하면 사람이 읽기 쉬운 형식으로 출력

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
- `디렉터리`별로 `디스크 사용량`을 확인 
- `-h` 옵션을 사용하면 사람이 읽기 쉬운 형식으로 출력

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
- 현재 `실행 중인 프로세스`를 확인
- `ps -ef | grep <프로세스 이름>`을 주로 사용
- `-aux` 옵션을 사용하면 시스템에서 실행 중인 모든 프로세스와 자세한 정보를 출력

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
- 프로세스를 종료 
- 프로세스 ID(PID)를 사용하여 특정 프로세스를 종료할 수 있음 
- `-9` 옵션을 사용하면 강제종료 가능

> 예를 들어, 프로세스 ID가 2054인 프로세스를 종료하려면 다음과 같이 입력

```
[fedora@localhost ~]$ kill 2054
```

### `pstree`
- 부모 프로세스와 자식 프로세스의 관계를 트리 형태로 보여줌

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
- 웹에서 파일을 다운로드

> 예를 들어, 파일의 URL이 'https://linux.com/test.zip'인 경우 다음과 같이 입력

```
[fedora@localhost ~]$ wget https://linux.com/test.zip
```

### `curl`
- 웹에서 데이터를 송수신하거나 API를 호출하는 데 사용되는 명령어

> 예를 들어, 웹 페이지의 HTML 소스를 출력하려면 다음과 같이 입력

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
- 파일이나 디렉터리를 압축하거나 압축을 해제
- 동작: c(묶기), x(풀기), t(경로확인)
- 옵션: f(파일, *필수옵션), v(과정보기), J(tar+xz), z(tar+gzip), j(tar+bzip2)
- 파일압축(xz) 하기
```
[fedora@localhost ~]$ tar cvfJ mytest.tar.xz testzip2
testzip2

[fedora@localhost ~]$ ls
mytest.tar.xz  test  testzip  testzip2 

```
- 파일압출(xz) 풀기
```
[fedora@localhost ~]$ ls
mytest.tar.xz  test  testzip

[fedora@localhost ~]$ tar xvfJ mytest.tar.xz
testzip2

[fedora@localhost ~]$ ls
mytest.tar.xz  test  testzip  testzip2
```