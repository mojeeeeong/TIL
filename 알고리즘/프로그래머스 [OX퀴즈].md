# 프로그래머스 [OX퀴즈]
```python
def solution(quiz):
    answer = []
    for i in quiz:
        cal = i.split()
        if cal[1] == "+":
            if int(cal[0]) + int(cal[2]) == int(cal[4]):
                answer.append("O")
            else:
                answer.append("X")
        else:
            if int(cal[0]) - int(cal[2]) == int(cal[4]):
                answer.append("O")
            else:
                answer.append("X")
        
    return answer
```
