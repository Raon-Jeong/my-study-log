# import / for in range

```python
import turtle as t

#삼각형 그리기

for x in range(3):
    t.forward(100)
    t.left(120)

#사각형 그리기
for x  in range(4):
    t.forward(100)
    t.left(90)

#원 그리기
t.circle(50)
```

## for x in range (n) :
 - 변수 x의 값을 0,1,2 ... ,n-1로 바꾸면서 반복 블록을 실행하라
 - : 은 반복할 영역의 시작을 표시함 (빠트리지 않기!!)
 - 들여쓰기는 반복할 문장이 어디까지인지 알려줌

## import 명령어 
   : 이미 만들어진 모듈 or 패키지를 코드에서 사용하겠음.
### ① import 모듈명
   - 모듈 전체를 가져옴
### ② from 모듈명 import 기능명
   - 특정 기능만 사용할 때
   - 모듈 이름이 길거나, 특정 함수를 자주 사용할 때
### ③ import 모듈명 as 별명
   - 모듈 이름이 길 때
   - 데이터 분석처럼 업계 표준으로 굳어진 별명이 있을 때
### ④ from 모듈명 import *
   - *은 모든 것을 뜻함
   - 모듈 안의 모든 것을 다 가져올 때
