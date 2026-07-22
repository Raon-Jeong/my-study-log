# if else를 이용한 문제 풀기

## 문제
```
마트 계산대 프로그램 입니다.
10000원짜리 추석선물세트를 구입했을 때 지불해야하는 금액을 계산해보세요.
단 11개 이상 구매시에는 10% 할인이 됩니다.
```

## 풀이
```python
n = 10000
a = n * s

if s > 10 :
    a = a * 0.9

print(a)
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
/tmp/ipykernel_585/2708524666.py in <cell line: 0>()
      1 n = 10000
----> 2 a = n * s
      3 
      4 if s > 10 :
      5     a = a * 0.9

NameError: name 's' is not defined
```
```python
n = 10000
a = n * s
s = int(input())

if s > 10 :
    a = a * 0.9

print(a)
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
/tmp/ipykernel_585/3056680664.py in <cell line: 0>()
      1 n = 10000
----> 2 a = n * s
      3 s = int(input())
      4 
      5 if s > 10 :

NameError: name 's' is not defined
```
```python
n = 10000
s = int(input())
a = n * s

if s > 10 :
    a = a * 0.9

print(a)
---------------------------------------------------------------------------
12
108000.0
```
## 배운점
- 모든 변수는 명확히 정의 되어야 함
- 위에서 아래로 내려오는 순서를 항상 기억하여 변수도 순서대로 배치해야함
