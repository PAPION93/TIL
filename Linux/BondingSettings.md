# CentOS 7 Bonding Settings

`vi /etc/sysconfig/network-scripts/ifcfg-bond0`

    TYPE=Bond
    DEVICE=bond0
    IPADDR=
    NETMASK=
    GATEWAY=
    ONBOOT=yes
    BOOTPROTO=none
    USERCTL=no
    BONDING_OPTS="mode=1 miimon=100 fail_over_mac=0"
    UUID=

## ✔ 절체 테스트 진행

- `eno1 down` ➡ `eno2` Active 정상 확인.
  - 명령어 `cat /proc/net/bonding/bond0`
- `eno1 up` ➡ `eno2 down` ➡ `eno1` Active 정상 확인하였으나 외부통신이 안됨.
- 스위치의 주소테이블에는 해당 포트의 `mac address`가 아직 `eno2` 의 `mac address` 인 것을 확인
  - `systemctl restart network` 전까지는 진전이 없거나, 스위치 learning 주기 초과시 연결됨
- `fail_over_mac=0` 설정을 통해 `eno1`과 `eno2`의 스위치와 주고받는 `mac address`를 통일시켜 스위치에서 바로 찾을 수 있도록 함
  - `1`은 고유의 `mac address`를 가지고 통신

`vi /etc/sysconfig/network-scripts/ifcfg-eno1, ifcft-eno2`

    TYPE=Ethernet
    BOOTPROTO=none
    NAME=
    UUID=
    DEVICE=
    ONBOOT=yes
    USERCTL=no
    MASTER=bond0
    SLAVE=yes

`vi /etc/modprobe.d/bonding.conf`

    alias bond0 bonding
    alias bond1 bonding

`vi /etc/sysconfig/network`

    NETWORKING=yes
    HOSTNAME=
    GATEDEV=bond0
