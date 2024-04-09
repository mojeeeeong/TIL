# SWEA [숫자 카드]
```python
T = int(input())    #테스트 케이스 수를 받는다.

for tc in range(1, T+1):    #테스트 케이스 수만큼 돌린다.
    N = int(input())    #카드 장수가 주어진다.
    L = input()     #여백없는 N개의 숫자가 주어진다.(str)
    num = 0     #가장 많은 카드 숫자
    cnt = 0     #가장 많은 카드 장 수
    for i in L: #N개의 숫자를 반복
        if L.count(i) >= cnt and int(i) > num:   #우선 개수가 동등하거나 많고 and 숫자도 크면
            num = int(i)    
            cnt = L.count(i)
            
    print(f'#{tc} {num} {cnt}')
```
