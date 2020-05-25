# 끝내주는 리눅스 명령어 모음

> 새로이 알게된, 기존에 알던 리눅스 명령어 사전

---

## 콘솔 단축키

1. 커서 처음, 끝으로 이동

   - `Ctrl + A , E`

2. 다음, 이전 명령어

   - `Ctrl + P, N`

3. 키보드 잠금, 해제

   - `Ctrl + S, Q`

4. history 검색

   - `Ctrl + R`

## 네트워크

1. network throughput(Rx, Tx KB/s)을 측정

   - `sar -n DEV 1`

2. Ring Buffer

   - 사이즈 확인
   - `ethtool -g|--show-ring devname`
   - 사이즈 설정
   - `ethtool -G|--set-ring devname [rx N] [tx N]`

## VI

1. 되돌리기와 되돌리기 취소

   - `u , Ctrl + r`
