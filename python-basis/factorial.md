### factorial 함수
```python
def factorial(n) :
    fact = 1
    for x in range(1, n+1) :
        fact = fact * x
    return fact

print(factorial(5))
print(factorial(10))
```
- 1 ~ n까지 모든 정수를 곱한 값
