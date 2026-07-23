# 문자열 세로 프린트

## 문제
```
Q. 문자열 str이 주어집니다.
   문자열을 시계방향으로 90도 돌려서 아래 입출력 예와 같이 출력하는 코드를 작성해 보세요.

※ 제한사항 ※
   1 <= str의 길이 <= 10

※ 입출력 예 ※
- 입력 #1
  abcde

- 출력 #1
  a
  b
  c
  d
  e
```
## 주어진 코드
```python
str = input( )
```
## 나의 풀이
```python
str = list(input())
if 1 <= len(str) <= 10 :
        print(range(str))
------------------------------------------------------------------------------------------------
Traceback (most recent call last):
  File "/solution.py", line 5, in <module>
    print(range(str))
          ~~~~~^^^^^
TypeError: 'list' object cannot be interpreted as an integer
```
```python
str = list(input())
if 1 <= len(str) <= 10 :
        print(str)
------------------------------------------------------------------------------------------------
실행한 결괏값 ['a', 'b', 'c', 'd', 'e']이 기댓값 a과 다릅니다.
```
```python
str = list(input())
n = 0
if 1 <= len(str) <= 10 :
    print(str[n])
    n = n + 1
------------------------------------------------------------------------------------------------
실행 결과 〉	Output size differs
출력 〉	a
```
```python
str = list(input())
n = 0
if 1 <= len(str) <= 10 :
    while n < len(str) :
        print(str[n])
    n = n + 1
------------------------------------------------------------------------------------------------
출력한 내용이 너무 깁니다.
```
```python
str = list(input())
n = 0
if 1 <= len(str) <= 10 :
    while n < len(str) :
        print(str[n])
        n = n + 1
------------------------------------------------------------------------------------------------
출력 〉
a
b
c
d
e
```
## 다른 사람 풀이
①
```python
print('\n'.join(input()))

# join을 이용해 각 글자 사이에 \n을 넣어 바로 출력
# 글자들 사이에 \n을 넣어 하나의 큰 문자열로 합친 뒤 한번에 출력
```
②
```python
for a in input():
    print(a)

# for_in을 사용하여 입력받은 문자열에서 하나씩 변수 a에 저장해서 출력
# 한 글자씩 순차적으로 하나씩 출력
```
③
```python
str = list(input())
for i in range(len(str)):
    print(str[i] )

# str에 입력된 내용을 list형태로 저장 후 for문에서 indexing을 활용하여 입력된 내용을 한글자씩
  순서대로 출력
# range 안의 숫자와 index번호 둘 다 0 ~ n-1인걸 사용
```
## 배운 것
### join( )
 - "구분자".join( )
 - 리스트나 튜플 안에 들어있는 여러 개의 문자열 요소들을 하나로 합쳐서 하나의 큰 문자열로 만들어주는 함수
 - 구분자 = 연결할 문자열 : 각 요소들 사이에 들어가는 접착제 역할
### \n
 - 줄바꿈을 나타내는 이스케이프 문자의 일종
 - " "안에서 사용해야 적용됨
 - 연속해서 쓰면 여러 줄을 비울 수 있음.
### for...in
 - 대상에서 요소를 하나씩 순서대로 꺼내서 변수에 담아주는 역할
