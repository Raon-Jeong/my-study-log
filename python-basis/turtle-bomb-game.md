# 표준 코드 배치 순서
   ### 1. import
   - 필요한 외부 라이브러리 불러오기
   - ex) import turtle, import random
   ### 2. Constants & Variables
   - 게임의 규칙, 초기 위치, 점수 등 설정값(변수) 정의
   ### 3. Function
   - 게임 ㄹ안에서 일어날 기능(함수) 정의
   - ex) def fire( ), 점수 계산 등
   ### 4. Main Logic (UI/Drawing)
   - 화면 디자인, 캐릭터 배치 등 실제 눈에 보이는 프로그램 실행
   ### 5. Event Listeners
   - 키보드, 마우스 입력 연결 및 프로그램 무한 루프 시작
   - ex) listen( )

## 책 실습 예제
```python
import turtle as t
import random

def turn_up() :
    t.left(2)

def turn_down() :
    r.right(2)

def fire() :
    ang = t.heading()
    while t.ycor() > 0 :
        t.forward(15)
        t.right(5)

    d = t.distance(target, 0)
    t.sety(random.randint(10, 100))
    if d < 25 :
        t.color("blue")
        t.write("Good!", False, "center", ("", 15))
    else :
        t.color("red")
        t.write("Bad!", False, "center", ("", 15))
    t.color("black")
    t.goto(-200, 10)
    t.setheading(ang)

t.goto(-300, 0)
t.down()
t.goto(300, 0)

target = random.randint(50, 150)

t.pensize(3)
t.color("green")
t.up()
t.goto(target - 25, 2)
t.down()
t.goto(target + 25, 2)

t.color("black")
t.up()
t.goto(-200, 10)
t.setheading(20)

t.onkeypress(turn_up, "Up")
t.onkeypress(turn_down, "Down")
t.onkeypress(fire, "space")

t.listen()
```

## 표준 코드 배치 순서 및 가독성 향상 연습
```python
#Import

import turtle as t
import random

#Constants & Variables

ENEMY_START_POS = 0, 200
FEED_START_POS = 0, -200
ANIMATION_SPEED = 0

#Function

def turn_right() :
    player_turtle.setheading(0)
    player_turtle.forward(10)

def turn_up() :
    player_turtle.setheading(90)
    player_turtle.forward(10)

def turn_left() :
    player_turtle.setheading(180)
    player_turtle.forward(10)

def turn_down() :
    player_turtle.setheading(270)
    player_turtle.forward(10)

def play() :
    ang = enemy_turtle.towards(player_turtle.pos())
    enemy_turtle.setheading(ang)
    enemy_turtle.forward(9)
    if player_turtle.distance(feed_turtle) < 12 :
        new_feed_pos_x = random.randint(-230, 230)
        new_feed_pos_y = random.randint(-230, 230)
        feed_turtle.goto(new_feed_pos_x, new_feed_pos_y)
    if player_turtle.distance(feed_turtle) >= 12 :
        t.ontimer(play, 100)

#Main Logic

t.setup(500,500)
t.bgcolor("orange")

enemy_turtle = t.Turtle()
enemy_turtle.shape("turtle")
enemy_turtle.color("red")
enemy_turtle.speed(ANIMATION_SPEED)
enemy_turtle.up()
enemy_turtle.goto(ENEMY_START_POS)

player_turtle = t.Turtle()
player_turtle.shape("turtle")
player_turtle.speed(ANIMATION_SPEED)
player_turtle.up()
player_turtle.color("white")

feed_turtle = t.Turtle()
feed_turtle.shape("circle")
feed_turtle.color("green")
feed_turtle.speed(ANIMATION_SPEED)
feed_turtle.up()
feed_turtle.goto(FEED_START_POS)

#Event listners

t.onkeypress(turn_right, "Right")
t.onkeypress(turn_up, "Up")
t.onkeypress(turn_left, "Left")
t.onkeypress(turn_down, "Down")

t.listen()

play()
```

### 바꾼점
   - 각 거북이 역할에 맞게 이름 부여
   - 모듈 별명과 객체 구분
   - 코드 배치 구역에 맞게 재배치
   - play 함수에서 t.forward(10)빼서 player_turtle이 키입력을 받았을 때만 움직이게 함

### 주의할 점
   - Constants & Variables에서 위치 지정할 때는 ( )빼고 작성해야함
   - 게임의 speed는 Constants & Variables에 지정해놔야 후에 수정할 때 편함
   - 각 키를 눌렀을 때 움직이게 하려면 키를 눌렀을 때 실행되는 함수에 꼭 각각 .forward 넣어야 함
   - 라이브러리 명령어 구분 잘하기

### t.write(출력 내용, t 이동여부, 정렬방식, 글꼴설정)
