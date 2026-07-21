# range(a, b)와 random.randint(a, b)
```python
import turtle as t
import random

t.shape("turtle")
t.speed(0)

for x in range(500) :
    a = random.randint(1, 360)
    t.setheading(a)
    t.forward(10)
```
## range(a, b)
   : for 반복문에서 a부터 b-1까지 정수를 하나씩 반복
## random.randint(a, b)
   : a부터 b까지의 임의의 정수를 만들어냄.
