# 프로그래머스 [n의 배수 고르기]
```python
def solution(n, numlist):
    answer = []
    for i in numlist:
        if i % n == 0:
            answer.append(i)
    return answer
```
