# 두 수의 차 구하기
## 문제
```
Q. 정수 num1과 num2가 주어질 때, num1에서 num2를 뺀 값을 return하도록 solution함수를 완성해주세요.

※ 제한사항 ※
   - 50000 <= num1 <= 50000
   - 50000 <= num2 <= 50000

※ 입출력 예 ※
- 출력 #1
  100 - 2 = 98
```
## 주어진 코드
```python
def solution(num1, num2):
    answer = 0
    return answer
```
## 나의 풀이
```python
num1 = 2
num2 = 3

def solution(num1, num2) :
    answer = num1 - num2
    return answer

result = solution(num1, num2)
print(result)
--------------------------------------------------------------------------------------------------------
-1
```
## 다른 사람 풀이
```python
def solution(num1, num2):
    return num1 - num2

print(solution(2,3))
--------------------------------------------------------------------------------------------------------
-1
```
## 배운 것
- return
  - 함수 내부에서 사용되는 키워드로 함수의 실행 즉시 종료와 호출한 곳으로 값을 전달함.
  - 함수안에 식을 쓰고 return해주지 않으면 그 식은 밖에서 그 함수를 호출해도 적용되지 않음.
