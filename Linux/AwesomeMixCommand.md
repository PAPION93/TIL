# 끝내주는 리눅스 명령어 모음
> 새로이 알게된, 기존에 알던 리눅스 명령어 사전  

---

## 네트워크
1. sar -n DEV 1
> network throughput(Rx, Tx KB/s)을 측정할수 있다.  

2. ethtool -g eth0
> eth0의 Ring Buffer를 확인할 수 있다.  
> `ethtool -G eth1 rx 1020` 과 같이 설정가능하다.
