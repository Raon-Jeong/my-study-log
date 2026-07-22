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
## 선생님 풀이
```python
prod = int(input("사려는 상품의 개수 : "))
if prod >= 11 :
    print(f"가격은 {prod * 9000}원 입니다.")
else :
    print(f"가격은 {prod * 10000}원 입니다.")
---------------------------------------------------------------------------
사려는 상품의 개수 : 12
가격은 108000원 입니다.
```

## 배운점
  ### - 모든 변수는 명확히 정의 되어야 함
  ### - 위에서 아래로 내려오는 순서를 항상 기억하여 변수도 순서대로 배치해야함
  ### - indexing 
   - 연속된 데이터 중에서 단 하나의 요소를 가리키는 것.
   - [ ]로 사용
  ```python
  text = "PYTHON"

  # 양수 인덱싱 (앞에서부터)
  print(text[0])  # 'P' (첫 번째)
  print(text[2])  # 'T' (세 번째)

  # 음수 인덱싱 (뒤에서부터)
  print(text[-1])  # 'N' (맨 뒤)
  print(text[-2])  # 'O' (뒤에서 두 번째)
  ```
  ### - slicing
   - 데이터를 범위 지정하여 잘라내는 것.
   - 단일 요소가 아닌 연속된 부분 집합을 가져올 때 사용.
   - [ ]로 사용
   - 기본 문법 : 자료형[시작 인덱스 : 끝 인덱스 : 증감값]
  ```python
text = "PYTHON"

# 1. basic slicing : [시작 : 끝]
print(text[0:3])  # 'PYT' (0, 1, 2번 인덱스 추출 / 3번은 미포함!)

# 2. 생략 문법
print(text[:3])   # 'PYT' (처음부터 3 전까지)
print(text[2:])   # 'THON' (2부터 끝까지)
print(text[ : ])  # 'PYTHON' (전체 복사)

# 3. 증감값(step) 활용
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(numbers[::2])   # [0, 2, 4, 6, 8]
print(numbers[::-1])  # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0] (전체 거꾸로 뒤집기)
```
  ### - formatting
   - 문자열 안에 변수나 계산 결과를 자연스럽게 넣어 표현하는 방법
   - 문자열 앞에 f를 붙이고, 넣을 변수나 식을 { } 안에 넣음.
```python
name = "민수"
age = 20
print(f"안녕하세요, 제 이름은 {name}이고 나이는 {age}살입니다.")

# 중괄호 안에서 연산 가능
print(f"내년 나이: {age + 1}")

# 소수점 자릿수 지정 (소수점 둘째 자리까지)
pi = 3.141592
print(f"원주율: {pi:.2f}")  # 출력: 원주율: 3.14
```
  ### - list
   - 여러개의 데이터를 순서대로 묶어서 저장하는 데이터 구조
   - tuple과 달리 값을 자유롭게 수정, 추가, 삭제 가능
   - 숫자, 문자열, 다른 list 등 다양한 데이터를 함께 담을 수 있음.
   - [ ]로 사용
   - 내부는 , 로 구분함
   - 요소가 몇개 들어갈지 명확하지 않을 때 사용
```python
# 리스트 생성
fruits = ["사과", "바나나", "체리"]

# 1. 인덱싱 & 슬라이싱
print(fruits[0])      # '사과'
print(fruits[1:])     # ['바나나', '체리']

# 2. 값 수정
fruits[1] = "포도"
print(fruits)         # ['사과', '포도', '체리']

# 3. 데이터 추가 및 삭제 (주요 메서드)
fruits.append("오렌지") # 맨 뒤에 추가
print(fruits)          # ['사과', '포도', '체리', '오렌지']

fruits.remove("사과")   # 특정 값 삭제
print(fruits)          # ['포도', '체리', '오렌지']
```
  ### - tuple
   - list와 비슷하게 여러개의 데이터를 순서(index)대로 묶어서 저장하는 데이터 구조
   - list와 달리 추가, 수정, 삭제 불가능함
   - ( )로 사용
   - 내부는 , 로 구분함
   - 데이터의 변경을 막아 프로그램의 안정성을 높이거나, 고정된 정보를 전달할 때 사용
   - 요소 개수를 사전에 정확히 알고 있을 때 사용
```python
# 튜플 생성
menu = ("아메리카노", "카페라떼", "바닐라라떼")

# 인덱싱과 슬라이싱 (가능)
print(menu[0])       # '아메리카노'
print(menu[1:])      # ('카페라떼', '바닐라라떼')

# 값 수정 시도 (에러 발생!)
# menu[0] = "디카페인"  -> TypeError 발생 (수정 불가)
```
### - dictionary
   - 여러개의 데이터를 사전처럼 관리하는 구조
   - 순서가 없는 대신, key를 이용해 원하는 value를 빠르게 찾을 수 있음.
   - kye와 value를 한쌍으로 갖는 자료형
   - { }로 사용
   - indexing, slicing불가
   - dictionary명 = {key1 : value1, key2 : value2}
```python
# 딕셔너리 생성
person = { "name": "홍길동", "age": 25, "city": "서울"}

# Key를 통한 데이터 조회 (인덱싱 대신 사용)
print(person["name"])  # '홍길동'
print(person["age"])   # 25

# 값 추가 및 수정 (가능)
person["age"] = 26             # 기존 Key의 Value 수정
person["job"] = "개발자"        # 새로운 Key:Value 추가
print(person)  # {'name': '홍길동', 'age': 26, 'city': '서울', 'job': '개발자'}
```
