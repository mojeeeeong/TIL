# 프로그래머스 [k의 개수]
```python
def solution(i, j, k):
    answer = 0
    num = ''        # 문자로 한번에 다 더해주기 위해
    for i in range(i, j + 1):   # 주어진 숫자 범위만큼
        num += str(i)           # 문자열로 형변환 후 num에 더해준다.
    
    answer = num.count(str(k))  # 다 더해준 num에서 원하는 값 k가 몇 개인지 확인
    return answer
```
