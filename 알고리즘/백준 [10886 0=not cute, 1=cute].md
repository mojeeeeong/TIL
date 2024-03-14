# 백준 [10886 0=not cute, 1=cute]
```python
N = int(input())    #설문조사한 사람 수
cute = 0            #투표 수를 비교하기 위해 변수를 2개 설정
no_cute = 0
for _ in range(N):  #설문조사한 사람 수만큼 반복
    A = int(input())    #설문조사한 값을 받는다.
    if A == 1:          #설문조사한 값이 1이면
        cute += 1       #cute변수에 1을 더해라
    else :              #설문조사한 값이 0이면
        no_cute += 1    #no_cute변수에 1을 더해라
if cute > no_cute:
    print("Junhee is cute!")
elif cute < no_cute:
    print("Junhee is not cute!")
```
