# 홀짝 구분
## 문제
```
Q. 자연수 n이 입력으로 주어졌을 때 만약 n이 짝수이면 "n is even"을, 홀수이면 "n is odd"를 출력하는 코드를 작성해 보세요.

※ 제한사항 ※
   1 <= n <= 1000

※ 입출력 예 ※
- 입력 #1
  100
- 출력 #1
  100 is enven
```
## 주어진 코드
```python
a = int(input( ))
```
## 나의 풀이
```python
a = int(input())
n = 0
while 1 <= a <= 1000 :
    if a == 2 * n :
        print("is even")
        break
    if a == 2 * n + 1 :
        print("is odd")
        break
    n + 1
-----------------------------------------------------------------------------------------------------------
실행 시간이 10.0초를 초과하여 실행이 중단되었습니다. 실행 시간이 더 짧은 다른 방법을 찾아보세요.
```
```python
a = int(input())
n = 0
while 1 <= a <= 1000 :
    n = 0
    if a == 2 * n :
        print(f"{a} is even")
        break
    if a == 2 * n + 1 :
        print(f"{a} is odd")
        break
    n + 1
-----------------------------------------------------------------------------------------------------------
실행 시간이 10.0초를 초과하여 실행이 중단되었습니다. 실행 시간이 더 짧은 다른 방법을 찾아보세요.
```
```python
a = int(input())
while 1 <= a <= 1000 :
    if a%2 == 0 :
        print(f"{a} is even")
    else :
        print(f"{a} is odd")
    break
```

## 다른 사람 풀이
①
```python
N = int(input())
print(f"{N} is {'even' if N % 2 == 0 else 'odd'}")

# print를 먼저 쓰고, f안의 변수 안에 if/else문을 넣음
```
②
```python
n = int(input())
print(f"{n} is odd" if n % 2 else f"{n} is even")

# print안에 if문을 넣음.
```
