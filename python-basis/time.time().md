# time.time( )
```python
import time

input("엔터를 누르고 20초를 셉니다.")
start = time.time()

input("20초 후에 다시 엔터를 누릅니다.")
end = time.time()

et = end - start
print("실제 시간 :", et, "초")
print("차이 :", abs(et - 20), "초")
```
- time.time() : 컴퓨터 방식으로 현재의 시, 분, 초를 측정
  => unix time / epoch time 형태로 나옴
  => 코드 실행 시간 측정 or 시간 간격 계산할 때 흔하게 사용

- abs( ) : 부호가 사라진 절대값을 구해줌.
