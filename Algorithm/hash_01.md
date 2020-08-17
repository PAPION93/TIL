> 프로그래머스 코딩테스트  
> [해시 > 완주하지 못한 선수](https://programmers.co.kr/learn/courses/30/lessons/42576)

# 해시 테이블
해시 테이블(해시 맵)은 키를 값에 매핑할 수 있는 구조인 연관 배열 추상 데이터 유형(associative array abstract data type)을 구현하는 자료구조이다.  
해시 테이블은 해시 함수를 사용하여 색인을 버킷이나 슬롯의 배열로 계산한다.

![hash_table](https://github.com/PAPION93/TIL/blob/master/img/hash_table.png)  
*출처: 위키백과-해시테이블*


```
def solution(participant, completion):
    participant.sort()
    completion.sort()

    for i in range(len(completion)):
        if completion[i] != participant[i]:
            return participant[i]

    return participant[len(participant)-1]
```