# 프로그래머스 [A로 B 만들기]
```python
def solution(before, after):
    answer = 0
    
    # before, after 각각 정렬
    before_list = sorted(list(before))
    after_list = sorted(list(after))
    
    # 반복문 돌리면서 요소 및 요소 순서가 같은지 확인
    for i in range(len(before)):
        if before_list[i] == after_list[i]:
            answer = 1
        else:
            
            # 다르다면 순서를 바꾸더라도 만들 수 없으므로 바로 break
            answer = 0
            break
    
    return answer
```
생각해보니 리스트로 변환해서 정렬을 할 필요 없이                            
문자열 자체를 정렬해서 비교해도 괜찮을 것 같다.                      
```python
def solution(before, after):
    before = sorted(before)
    after = sorted(after)
    if before == after:
        return 1
    else:
        return 0
```
