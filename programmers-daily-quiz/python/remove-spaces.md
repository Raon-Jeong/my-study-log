# 문자열 붙여서 출력하기
## 문제
```
Q. 두개의 문자열 str1, str2가 공백으로 구분되어 입력으로 주어집니다.
   입출력 예와 같이 str1과 str2를 이어서 출력하는 코드를 작성해 보세요.

※ 제한 사항 ※
  - 1 <= str1, str2의 길이 <= 10

※ 입출력 예 ※
   입력 #1
   apple pen
   출력 #1
   applepen
```
## 준비된 코드
```python
str1, str2 = input().strip().split(' ')
print( )
```
## 나의 풀이
```python
str1, str2 = input().strip().split(' ')
W = str1, str2
print(w.replace(" ", ""))
----------------------------------------------------------------------------------------------------
Traceback (most recent call last):
  File "/solution.py", line 5, in <module>
    print(w.replace(" ", ""))
          ^^^^^^^^^
AttributeError: 'tuple' object has no attribute 'replace'
```
```python
str1, str2 = input().strip().split(' ')
print((str, str2).replace(" ",""))
----------------------------------------------------------------------------------------------------
Traceback (most recent call last):
  File "/solution.py", line 4, in <module>
    print((str, str2).replace(" ",""))
          ^^^^^^^^^^^^^^^^^^^
AttributeError: 'tuple' object has no attribute 'replace'
```
```python
str1, str2 = input().strip().split(' ')
if 1 <= len(str1) <= 10 and 1 <= len(str2) <= 10 :
    w = (str1 + str2).replace(" ","")
print(w)
```
## 다른 사람 풀이 
①
```python
print(input().strip().replace(' ', ''))

# str 필요없이 그냥 입력받은 문장 그대로 공백들 다 없애서 프린트 해도 됨.
```
②
```python
str1, str2 = input().strip().split(' ')
print(str1 + str2)

# 파이썬에서 +연산자로 문자열을 더하면 그대로 공백없이 붙여서 하나의 문자열로 만들어 줌.
```
## 배운 것
- split(' ')

  : 문자열을 공백하나를 기준으로 쪼개서 리스트를 만듦.

- strip( )

  : 입력받은 문자열의 양 끝에 있는 공백과 줄바꿈 문자를 제거함.

- 문자열.replace("찾을 문자열", "바꿀 문자열")

  : 특정 글자 or 단어를 찾아 다른 글자  or 단어로 바꾸어줌
