# 백준 [10214 Baseball]
```python
T = int(input())    #테스트 케이스 수
for _ in range(T):   #테스트 케이스 수만큼 반복
    Y = 0       #연세대 총 점수 0으로 시작
    K = 0       #고려대 총 점수 0으로 시작
    for _ in range(9):    #하나의 테스트케이스에 9번 입력되므로
        a, b = map(int, input().split())    #연세대, 고려대 점수를 각각 받는다.
        Y += a      #연세대 점수를 더한다.
        K += b      #고려대 점수를 더한다.
    if Y > K :      #연세대가 이겼으면
        print("Yonsei")
    elif Y < K :    #고려대가 이겼으면
        print("Korea")
    else :          #비겼으면
        print("Draw")
```
