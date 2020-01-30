# Packet dropped 

NIC 내의 Ring Buffer가 Full되면 drop이 발생하게되는데, 
Ring Buffer의 크기를 늘려줌으로써 원인을 제거할 수 있다.  

![](https://github.com/PAPION93/TIL/blob/master/img/RingBuffer.jpg)

## Ring Buffer
 - FIFO 기반 동작
 - 서버로 전달되는 패킷은 NIC내의 Ring Buffer에 보관되고 그 후 커널의 Sockect RCV Buffer로 이동한다. 그 이후 App의 read를 통해 전달 된다.

 - Ring Buffer 값을 확인 방법
    - `ethtool -g|--show-ring devname`
 - Ring Buffer 설정 방법
    - `ethtool -G|--set-ring devname [rx N] [tx N]`

## dropwatch
 - 커널이 드롭한 패킷을 감시하는 모니터링 유틸리티.