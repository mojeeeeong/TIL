# SWEA [거듭 제곱]
```python
for _ in range(10): #10개의 테스트 케이스
    T = int(input())    #테스트 케이스 숫자를 받는다.
    N, M = map(int, input().split())    #N의 M 거듭제곱을 구하기 위해
    sum = 1     #초기값을 1로 둔다.(곱해야하기 때문에)
    for i in range(M):  #M번 거듭제곱
        sum *= N
    print(f'#{T} {sum}')
```
