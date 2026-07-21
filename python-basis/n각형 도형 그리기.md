# turtle을 이용한 n각형 도형 그리기
```python
import turtle as t

n = 5
t.color("purple")
t.begin_fill()
for x in range(n) :
    t.forward(50)
    t.left(360/n)
t.end_fill()
```
- n각형 도형의 외부 각의 합은 365임을 이용하여 t.left(360/n)을 함.
