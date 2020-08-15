> 프로그래머스 코딩테스트  
> [해시 > 완주하지 못한 선수](https://programmers.co.kr/learn/courses/30/lessons/42576)


```
def solution(participant, completion):
    participant.sort()
    completion.sort()

    for i in range(len(completion)):
        if completion[i] != participant[i]:
            return participant[i]

    return participant[len(participant)-1]
```