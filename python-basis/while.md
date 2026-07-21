# while 명령어
```python
import random

n = random.randint(1, 30)

while True :
    x = input("맞혀 보세요?")
    g = int(x)
    if g == n :
        print("정답")
        break
    if g < n :
        print("너무 작아요.")
    if g > n :
        print("너무 커요.")
```
    while 판단 조건 :
           반복 실행할 내용
- 판단 조건이 True인 동안 실행
  => while True : 영원히 반복
