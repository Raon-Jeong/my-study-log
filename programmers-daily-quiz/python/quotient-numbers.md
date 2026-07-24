# 두 수의 나눗셈
## 문제
```
Q. 정수 num1과 num2가 매개변수로 주어질 때, num1을 num2로 나눈 값에 1,000을 곱한 후
   정수 부분을 return하도록 solution 함수를 완성해주세요.

※ 제한사항 ※
- 0 < num1 <= 100
- 0 < num2 <= 100

※ 입출력 예 ※
#1
- num1이 3, num2가 2이므로 3/2 = 1.5에 1000을 곱하면 1500이 됩니다.
#2
- num1이 7, num2가 3이므로 7/3 = 2.3333333...에 1,000을 곱하면 2333,33333...이 되며,
  정수부분은 2333입니다.
```
## 주어진 코드
```python
def solution(num1, num2):
    answer = 0
    return answer
```
## 나의 풀이
```python
def solution(num1, num2):
    if 0 < num1 <= 100 and 0 < num2 <= 100 :
        answer = int(1000 * (num1 / num2))
        return answer
```
## 다른 사람 풀이
```python
def solution(num1, num2):
    return int(num1 / num2 * 1000)
```
