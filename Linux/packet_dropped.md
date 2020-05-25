# NIC Dropped Packet

NIC 내의 Ring Buffer가 Full되면 drop이 발생하게되는데,
Ring Buffer의 크기를 늘려주는 것이 원인 예방 중 하나의 방법이다.

![RingBuffer](https://github.com/PAPION93/TIL/blob/master/img/RingBuffer.jpg)

## Ring Buffer(원형 큐)

- FIFO 기반 동작
- 서버로 전달되는 패킷은 NIC내의 Ring Buffer에 보관되고 그 후 커널의 Sockect RCV Buffer로 이동한다.
- 마지막으로 App에서 read, recv로 빼낸다.

- Ring Buffer 값을 확인 방법
  - `ethtool -g|--show-ring devname`
- Ring Buffer 설정 방법
  - `ethtool -G|--set-ring devname [rx N] [tx N]`

## dropwatch

- 커널이 드롭한 패킷을 감시하는 모니터링 유틸리티.
