# 리눅스 시스템 관리

## 사용자 관리

### `useradd`
- 새로운 사용자 계정 `추가`
- 옵션:
  - `-m`: 사용자의 홈 디렉터리를 생성
  - `-d [디렉터리]`: 사용자의 홈 디렉터리를 지정
  - `-s [쉘]`: 사용자의 로그인 쉘을 지정
  - `-G [그룹1,그룹2,...]`: 사용자를 추가 그룹에 소속
  - `-u [UID]`: 사용자의 UID를 지정

> 예를 들어, 'newuser' 계정을 생성하고 홈 디렉터리를 '/home/newuser'로 지정하며 로그인 쉘을 '/bin/bash'로 설정하려면 다음과 같이 입력
```
[root@localhost ~]# useradd -m -d /home/newuser -s /bin/bash newuser
```

### `userdel`
- 사용자 계정 `삭제`
- 옵션: 
  - `-r`: 사용자의 홈 디렉터리와 메일 스풀도 함께 삭제

```
[root@localhost ~]# userdel -r newuser
```

### `passwd`
- 사용자 암호 설정 및 변경

```
[root@localhost ~]# passwd fedora
fedora 사용자의 비밀 번호 변경 중
새  암호:
```

### `id`
- 사용자의 UID, GID 및 소속 그룹을 확인할 수 있음

```
[root@localhost ~]# id fedora
uid=1000(fedora) gid=1000(fedora) groups=1000(fedora),10(wheel)
```

### `usermod`
- 명령어를 사용하여 사용자 계정 정보를 변경할 수 있음 
- 사용자의 로그인 쉘, 홈 디렉터리, 소속 그룹 등을 변경할 수 있음
- 옵션:
  - `-s`: 사용자의 로그인 쉘 변경
  - `-d`: 사용자의 홈 디렉터리 변경
  - `-m`: 기존의 홈 디렉터리를 새 위치로 이동
  - `-a -G`: 사용자를 여러그룹에 추가
  - `-g`: 사용자의 기본 그룹을 변경


> 'fedora'의 홈 디렉터리를 '/home/fedora1'로 변경하려면 다음과 같이 입력
```
[root@localhost ~]# usermod -d /home/fedora1 -m fedora
[root@localhost ~]# ls -l /home
합계 12
drwx------   3   1004 hanGroup 4096  3월 31 00:16 computer
drwx------. 16 fedora fedora   4096  4월 21 00:07 fedora1
drwxr-xr-x   2 root   root     4096  3월 31 00:30 myhome
```

> 'fedora'를 group1과 group2에 추가하려면 다음과 같이 입력
```
[root@localhost ~]# usermod -a -G group1,group2 fedora
[root@localhost ~]# id fedora
uid=1000(fedora) gid=1000(fedora) groups=1000(fedora),10(wheel),1005(group1),1006(group2)
```

> 'fedora'의 기본그룹을 group1으로 변경하려면 다음과 같이 입력
```
[root@localhost ~]# id fedora
uid=1000(fedora) gid=1000(fedora) groups=1000(fedora),10(wheel),1005(group1),1006(group2)

[root@localhost ~]# usermod -g group1 fedora

[root@localhost ~]# id fedora
uid=1000(fedora) gid=1005(group1) groups=1005(group1),10(wheel),1006(group2)

```

## 그룹관리

### `cat /etc/group`
- 현재 생성되어 있는 그룹 리스트 출력

```
[root@localhost ~]# cat /etc/group
```

### `groupadd`
- 새로운 그룹 생성

> 예를 들어, newFedoraGroup이라는 이름의 그룹을 생성하려면 다음과 같이 입력
```
[root@localhost ~]# groupadd newFedoraGroup
```

### `groupdel`
- 기존 그룹 삭제
- 그룹을 삭제하기 전에 그룹에 속한 모든 사용자를 다른 그룹으로 이동시켜야함
- 사용자를 이동시키지 않으면 시스템에 문제가 발생할 수 있음

> 예를 들어, newFedoraGroup이라는 이름의 그룹을 삭제하려면 다음과 같이 입력
```
[root@localhost ~]# groupdel newFedoraGroup
```

### `groupmod`
- 그룹 정보 수정
- 옵션: 
  - `-n`: 그룹 이름 변경
  - `-g`: 그룹 gid 변경

> 예를 들어, newFedoraGroup의 이름을 newFedoraGroup1으로 변경하려면 다음과 같이 입력

```
[root@localhost ~]# tail -7 /etc/group
fedora:x:1000:
fedoraGroup:x:1002:
hanGroup:x:1003:
etcGroup:x:1004:
group1:x:1005:fedora
group2:x:1006:fedora
newFedoraGroup:x:1007:

[root@localhost ~]# groupmod -n newFedoraGroup1 newFedoraGroup

[root@localhost ~]# tail -7 /etc/group
fedora:x:1000:
fedoraGroup:x:1002:
hanGroup:x:1003:
etcGroup:x:1004:
group1:x:1005:fedora
group2:x:1006:fedora
newFedoraGroup1:x:1007:
```

> 예를 들어, newFedoraGroup1의 GID를 2023으로 변경하려면 다음과 같이 입력
```
[root@localhost ~]# tail -1 /etc/group
newFedoraGroup1:x:1007:

[root@localhost ~]# groupmod -g 2023 newFedoraGroup1

[root@localhost ~]# tail -1 /etc/group
newFedoraGroup1:x:2023:
```

## 파일 시스템 관리
