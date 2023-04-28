# 리눅스 보안

## 방화벽 설정
- `방화벽(Firewall)`는 네트워크 보안을 강화하기 위한 기술 중 하나 
- 네트워크 상에서 수신되는 `패킷`을 `제어`하는 역할
- 방화벽의 기능: 
  - `패킷 필터링`: 방화벽은 수신되는 모든 패킷을 검사하고, 미리 설정된 규칙에 따라 패킷을 허용하거나 차단
  - `애플리케이션 필터링`: 방화벽은 네트워크 상에서 수행되는 애플리케이션에 대해 특정 규칙을 적용하여, 악성 코드나 해킹 등의 공격으로부터 보호
  - `가상 사설망 구성`: 방화벽은 가상 사설망(VPN)을 구성하여, 외부에서 안전하게 내부 네트워크에 접속할 수 있도록 함

### `iptables`
- 리눅스 커널의 내장 방화벽 기능을 제어하는 도구
- 네트워크 패킷의 송수신을 제어하며, 필터링 규칙을 설정할 수 있습니다. 

#### iptables의 기본 사용법
- 방화벽 규칙 목록 확인:
```
[root@localhost ~]# iptables -L
```
- 특정 포트 열기
```
iptables -A INPUT -p tcp --dport 포트번호 -j ACCEPT
```
```
[root@localhost ~]# iptables -A INPUT -p tcp --dport 8920 -j ACCEPT
[root@localhost ~]# iptables -L

Chain INPUT (policy ACCEPT)
target     prot opt source               destination         
ACCEPT     all  --  anywhere             anywhere             ctstate RELATED,ESTABLISHED
ACCEPT     all  --  anywhere             anywhere            
INPUT_direct  all  --  anywhere             anywhere            
INPUT_ZONES_SOURCE  all  --  anywhere             anywhere            
INPUT_ZONES  all  --  anywhere             anywhere            
DROP       all  --  anywhere             anywhere             ctstate INVALID
REJECT     all  --  anywhere             anywhere             reject-with icmp-host-prohibited
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:8920
``` 
- 특정 포트 차단
```
iptables -A INPUT -p tcp --dport 포트번호 -j DROP
```
```
[root@localhost ~]# iptables -A INPUT -p tcp --dport 8920 -j DROP
[root@localhost ~]# iptables -L

Chain INPUT (policy ACCEPT)
target     prot opt source               destination         
ACCEPT     all  --  anywhere             anywhere             ctstate RELATED,ESTABLISHED
ACCEPT     all  --  anywhere             anywhere            
INPUT_direct  all  --  anywhere             anywhere            
INPUT_ZONES_SOURCE  all  --  anywhere             anywhere            
INPUT_ZONES  all  --  anywhere             anywhere            
DROP       all  --  anywhere             anywhere             ctstate INVALID
REJECT     all  --  anywhere             anywhere             reject-with icmp-host-prohibited
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:8920
DROP       tcp  --  anywhere             anywhere             tcp dpt:8920
```
- 특정 IP 주소 차단
```
iptables -A INPUT -s IP주소 -j DROP
```
```
[root@localhost ~]# iptables -A INPUT -s 192.168.111.58 -j DROP
[root@localhost ~]# iptables -L

Chain INPUT (policy ACCEPT)
target     prot opt source               destination         
ACCEPT     all  --  anywhere             anywhere             ctstate RELATED,ESTABLISHED
ACCEPT     all  --  anywhere             anywhere            
INPUT_direct  all  --  anywhere             anywhere            
INPUT_ZONES_SOURCE  all  --  anywhere             anywhere            
INPUT_ZONES  all  --  anywhere             anywhere            
DROP       all  --  anywhere             anywhere             ctstate INVALID
REJECT     all  --  anywhere             anywhere             reject-with icmp-host-prohibited
ACCEPT     tcp  --  anywhere             anywhere             tcp dpt:8920
DROP       tcp  --  anywhere             anywhere             tcp dpt:8920
DROP       tcp  --  anywhere             anywhere             tcp dpt:sunwebadmins
DROP       all  --  192.168.111.58       anywhere  
```

- 방화벽 설정 저장
```
iptables-save > /etc/iptables/rules.v4 //CentOS, RHEL, Debian, Ubuntu에서만 가능
```

