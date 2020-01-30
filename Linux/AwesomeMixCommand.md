# 끝내주는 리눅스 명령어 모음
> 새로이 알게된, 기존에 알던 리눅스 명령어 사전  

---

## 네트워크
1. network throughput(Rx, Tx KB/s)을 측정  
 - `sar -n DEV 1`  

2. Ring Buffer  
 - Ring Buffer 사이즈 확인  
 - `ethtool -g|--show-ring devname`  
 - Ring Buffer 사이즈 설정  
 - `ethtool -G|--set-ring devname [rx N] [tx N]`  
