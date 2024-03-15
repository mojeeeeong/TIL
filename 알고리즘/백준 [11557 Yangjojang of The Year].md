# 백준 [11557 Yangjojang of The Year]
```python
T = int(input())        #테스트 케이스 수를 받는다.
for _ in range(T):      #테스트 케이스만큼 반복
    list1 = []          #리스트로 풀기 위해 받는다.
    list2 = []
    N = int(input())    #학교의 수
    for _ in range(N):  
        a, b = map(str, input().split())
        list1.append(a)         #list1에 학교 이름을 요소로 넣는다.
        list2.append(int(b))    #list2에 소비한 술의 양을 요소로 넣는다.
    print(list1[list2.index(max(list2))])
    #list2에서 최댓값의 인덱스를 받아와 그 인덱스 값을 list1에 적용하면 소비한 술의 양이 가장 많은 학교가 나온다.
```
