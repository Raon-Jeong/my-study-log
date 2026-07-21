# Turtle Run 게임 실습 및 표준코드배치 연습

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

## 표준 코드 배치 및 가독성 향상 연습
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
   - 각 거북이 역할에 맞게 이름부여
   - 모듈 별명과 객체 구분
   - 코드 배치 구역에 맞춰 재배치
   - message 글자 스타일 변경

### 주의할 점
   - Constants & Variables에서 정해놓은 것들 그대로 가져다 쓰기
   - player_turtle객체가 새로 생겼으므로 library명령어 잘 구분하고 화면에서 기본 t 숨기기

### 기억할 것
   - .setheading과 .towards는 절대각도를 사용함
   - 별도의 reset code를 넣지 않은 경우 실행을 하다 playing = False 상태로 돌아가면 게임만 멈춘 상태로 남음
   - if문 : 조건이 true일 때만 실행됨
   - .write("표시한 글자", 이동 여부, 정렬 위치, 폰트 스타일)
   - .write( ) : 객체 뒤에 쓰면 해당 객체를 따라다니고, 모듈명 뒤에 쓰면 화면 중앙(기본 위치) 기준으로 글씨가 적힘
   - python은 함수를 순서에 상관없이 등록만 함 ∴ 함수 순서 때문에 실행 오류가 나지는 않음
   - .speed( ) : 객체의 움직이는 속도가 아니라 애니메이션 연출 속도임 ∴ 모듈과 모든 객체에 적용해줘야함
   - .hideturtle( ) : 거북이 아이콘은 사라지고 글시나 선을 그리는 기능만 남게함
   - .home : 거북이를 초기 시작 위치인 원점(0, 0)으로 돌려보내고, 바라보는 방향도 기본방향 (동쪽, 0도)로 다시 세팅해줌
   - .setup : 그래픽이 그려질 윈도우 창의 크기와 위치를 설정함
      => .setup(width, heigh, startx, starty)
   - .ontimer(실행할 함수 이름, 시간) : 지정한 시간이 지난 후 특정 함수를 딱 한번만 실행하게 함
   - .ontimer : 시간 단위는 ms
      => ex) 1s = 1000ms
   - .title : 상단바에 나타낼 제목 
