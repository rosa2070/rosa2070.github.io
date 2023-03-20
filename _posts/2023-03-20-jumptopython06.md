---
layout: single
title:  "점프투파이썬 5장부터"
categories: coding
tag: [python, blog, jekyll]
toc: true
author_profile: false
---

<head>
  <style>
    table.dataframe {
      white-space: normal;
      width: 100%;
      height: 240px;
      display: block;
      overflow: auto;
      font-family: Arial, sans-serif;
      font-size: 0.9rem;
      line-height: 20px;
      text-align: center;
      border: 0px !important;
    }

    table.dataframe th {
      text-align: center;
      font-weight: bold;
      padding: 8px;
    }

    table.dataframe td {
      text-align: center;
      padding: 8px;
    }

    table.dataframe tr:hover {
      background: #b8d1f3; 
    }

    .output_prompt {
      overflow: auto;
      font-size: 0.9rem;
      line-height: 1.45;
      border-radius: 0.3rem;
      -webkit-overflow-scrolling: touch;
      padding: 0.8rem;
      margin-top: 0;
      margin-bottom: 15px;
      font: 1rem Consolas, "Liberation Mono", Menlo, Courier, monospace;
      color: $code-text-color;
      border: solid 1px $border-color;
      border-radius: 0.3rem;
      word-break: normal;
      white-space: pre;
    }

  .dataframe tbody tr th:only-of-type {
      vertical-align: middle;
  }

  .dataframe tbody tr th {
      vertical-align: top;
  }

  .dataframe thead th {
      text-align: center !important;
      padding: 8px;
  }

  .page__content p {
      margin: 0 0 0px !important;
  }

  .page__content p > strong {
    font-size: 0.8rem !important;
  }

  </style>
</head>


# 5장 파이썬 날개 달기


## 5-1 클래스


### 클래스는 왜 필요한가?



```python
result = 0

def add(num):
    global result
    result += num
    return result

print(add(3))
print(add(4))
```

<pre>
3
7
</pre>

```python
result1 = 0
result2 = 0

#계산기1
def add1(num):
    global result1
    result1 += num
    return result1

#계산기2
def add2(num):
    global result2
    result2 += num
    return result2
```


```python
print(add1(3))
print(add1(4))
print(add2(3))
print(add2(7))
```

<pre>
3
7
3
10
</pre>

```python
#클래스 사용
class Calculator:
    def __init__(self):
        self.result = 0
    
    def add(self, num):
        self.result += num
        return self.result
    
    #빼기 기능 추가
    def sub(self, num):
        self.result -= num
        return self.result
    
cal1 = Calculator()
cal2 = Calculator()
```


```python
print(cal1.add(3))
print(cal1.add(4))
print(cal2.add(3))
print(cal2.add(7))
```

<pre>
3
7
3
10
</pre>
### 클래스와 객체



```python
class Cookie:
    pass
```


```python
a=Cookie()
b=Cookie()
```

### 사칙연산 클래스 만들기


#### 클래스 구조 만들기



```python
class FourCal:
    pass
```


```python
a = FourCal()
```


```python
type(a) # a는 FourCal클래스의 객체
```

<pre>
__main__.FourCal
</pre>
#### 객체에 숫자 지정할 수 있게 만들기



```python
class FourCal:
    def setdata(self, first, second): # 1. 메서드의 매개변수
        self.first = first
        self.second = second #2.매서드의 수행문(first, second)
```

##### 1. setdata 메서드의 매개변수



```python
a = FourCal()
```


```python
# 메서드의 첫 번째 매개변수 self에는 setdata메서드를 호출한 객체 a가 자동으로 전달되기 때문에 first,second만 넣어주면 된다.
a.setdata(4,2)
```

##### 메서드의 또 다른 호출 방법



```python
# '클래스 이름.메서드' : 객체 a를 첫 번째 매개변수 self에 꼭 전달
a = FourCal()
FourCal.setdata(a,4,2) 
```


```python
# '객체.메서드' : self를 반드시 생략해서 호출
a = FourCal()
a.setdata(4,2)
```

##### 2. setdata 메서드의 수행문



```python
def setdata(self, first, second):
    self.first = first
    self.second = second #메서드의 수행문 (first, second)
```

```

a.setdata(4,2)호출하면

first, second에는 각각 값 4와 2가 전달되어

setdata 메서드의 수행문은 다음과 같이 해석

self.first = 4

self.second = 2



self는 전달된 객체 a이므로 다시 다음과 같이 해석

a.first = 4

a.second = 2

```


- a.first = 4 문장 수행 -> a 객체에 객체변수 first 생성 -> 값 4 저장

- a.second = 2 문장 수행 -> a 객체에 객체변수 second 생성 -> 값 2 저장



```python
a = FourCal()
```


```python
a.setdata(4,2)
```


```python
print(a.first)
```

<pre>
4
</pre>

```python
print(a.second)
```

<pre>
2
</pre>

```python
#a,b 객체 만들기
a = FourCal()
b = FourCal()
```


```python
#a객체의 객체변수 first 생성
a.setdata(4,2)
print(a.first)
```

<pre>
4
</pre>

```python
#b객체의 객체변수 first 생성
b.setdata(3,7)
print(b.first)
```

<pre>
3
</pre>

```python
# a 객체의 first 값은 b 객체의 first값에 영향받지 않고 원래 값 유지
print(a.first) 
```

<pre>
4
</pre>
- 클래스로 만든 객체의 객체변수는 다른 객체의 객체변수와 상관없이 독립적인 값 유지!!



```python
# 지금까지 완성된 FourCal 클래스
class FourCal:
    def setdata(self, first, second):
        self.first = first
        self.second = second
```

#### 더하기 기능 만들기



```python
class FourCal:
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
```


```python
a = FourCal()
```


```python
a.setdata(4,2)
```


```python
# add 메서드 호출
print(a.add())
```

<pre>
6
</pre>
- add 메서드 자세히 살펴보기



```python
def add(self):
    result = self.first + self.second
    return result
```


```python
# add 메서드의 매개변수는 self, 반환 값은 result
# 반환 값인 result를 계산하는 부분
result = self.first + self.second
```


```python
# a.add()와 같이 a 객체에 의해 add 메서드가 수행되면 add메서드의 self에는 객체 a가 자동입력되므로 위 내용은 다음과 같이 해석
result = a.first + a.second
```


```python
# 위 내용은 a.add() 메서드 호출 전 a.setdata(4,2)가 먼저 호출되어 
# a.first = 4, a.second = 2라고 미리 설정되었기에 다음과 같이 해석
result = 4 + 2
```


```python
print(a.add())
```

<pre>
6
</pre>
#### 곱하기, 빼기 ,나누기 기능 만들기



```python
class FourCal:
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
    def mul(self):
        result = self.first * self.second
        return result
    def sub(self):
        result = self.first - self.second
        return result
    def div(self):
        result = self.first / self.second
        return result
        
```


```python
a = FourCal()
```


```python
b = FourCal()
```


```python
a.setdata(4,2)
```


```python
b.setdata(3,8)
```


```python
a.add()
```

<pre>
6
</pre>

```python
a.mul()
```

<pre>
8
</pre>

```python
a.sub()
```

<pre>
2
</pre>

```python
a.div()
```

<pre>
2.0
</pre>

```python
b.add()
```

<pre>
11
</pre>

```python
b.mul()
```

<pre>
24
</pre>

```python
b.sub()
```

<pre>
-5
</pre>

```python
b.div()
```

<pre>
0.375
</pre>
### 생성자(Constructor)



```python
a = FourCal()
```


```python
a.add() # FourCal 클래스의 인스턴스 a에 setdata 메서드를 수행하지 않고  add 메서드를 수행하면 오류 발생
```

- 이렇게 객체에 초깃값을 설정해야 할 필요가 있을 때 : setdata 메서드 호출보다는 '생성자 구현'이 안전!!

- 생성자(Constructor) : 객체가 생성될 때 자동으로 호출되는 메서드

- 파이썬 메서드 이름으로 __init__을 사용하면 이 메서드는 생성자가 된다.



```python
#FourCal 클래스에 생성자 추가
class FourCal:
    def __init__(self, first, second):
        self.first = first
        self.second = second
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
    def mul(self):
        result = self.first * self.second
        return result
    def sub(self):
        result = self.first - self.second
        return result
    def div(self):
        result = self.first / self.second
        return result
```


```python
# 새롭게 추가된 생성자 __init__ 메서드만 따로 떼어 내서 살펴보기
def __init__(self, first, second):
    self.first = first
    self.second = second
```

- __init__ 메서드는 setdata 메서드와 이름만 다르고 모든 게 동일. 

- 단 메서드 이름을 __init__으로 했기 때문에 생성자로 인식되어 객체가 생성되는 시점에 자동으로 호출되는 차이



```python
# 생성자 first와 second에 해당하는 값이 전달되지 않아 오류 발생
a = FourCal() 
```


```python
a = FourCal(4,2)
```


```python
a = FourCal(4,2)
```


```python
print(a.first)
```

<pre>
4
</pre>

```python
print(a.second)
```

<pre>
2
</pre>

```python
a = FourCal(4,2)
```


```python
a.add()
```

<pre>
6
</pre>

```python
a.div()
```

<pre>
2.0
</pre>
### 클래스의 상속

- class 클래스 이름(상속할 클래스 이름)



```python
class MoreFourCal(FourCal):
    pass
```


```python
a = MoreFourCal(4,2)
```


```python
a.add()
```

<pre>
6
</pre>

```python
a = MoreFourCal(4,2)
```

- MoreFourCal 클래스는 FourCal 클래스를 상속했으므로 FourCal 클래스의 모든 기능 사용 가능



```python
a.add()
```

<pre>
6
</pre>

```python
a.mul()
```

<pre>
8
</pre>

```python
a.sub()
```

<pre>
2
</pre>

```python
a.div()
```

<pre>
2.0
</pre>

```python
class MoreFourCal(FourCal):
    def pow(self):
        result = self.first ** self.second
        return result
```


```python
a = MoreFourCal(4,2)
```


```python
a.pow()
```

<pre>
16
</pre>
#### 메서드 오버라이딩(Overriding, 덮어쓰기)

- 부모 클래스(상속한 클래스)에 있는 메서드를 동일한 이름으로 다시 만드는 것



```python
a = FourCal(4,0)
```


```python
a.div() #4를 0으로 나누려고 해서 오류 발생
```


```python
class SafeFourCal(FourCal):
    def div(self):
        if self.second == 0: # 나누는 값이 0인 경우 숫자 0을 돌려주도록 수정
            return 0
        else:
            return self.first/ self.second
```


```python
a = SafeFourCal(4,0)
```


```python
a.div()
```

<pre>
0
</pre>

```python
#### 상속과 변수 (super())
https://supermemi.tistory.com/178
```

#### 상속 super()



```python
#예시
class Nintendo:
    def __init__(self,name, character):
        self.country='Japan'
        self.game_name=name
        self.character=character
       
class New(Nintendo):
    def __init__(self,name,character,genre,income):
        super().__init__(name,character)
        self.ceo='Shigeru Miyamoto'
        self.genre=genre
        self.income=income 
        
p1 = New("simono", "warm", "mystery", 100)
print(p1.country, p1.game_name, p1.ceo, p1.income)
```

<pre>
Japan simono Shigeru Miyamoto 100
</pre>
### 클래스 변수

- 클래스이름.클래스변수



```python
class Family:
    lastname = "김" # 클래스 변수
```


```python
print(Family.lastname) 
```

<pre>
김
</pre>

```python
a = Family()
```


```python
b = Family()
```


```python
print(a.lastname)
```

<pre>
김
</pre>

```python
print(b.lastname)
```

<pre>
김
</pre>
- 클래스 변수 값을 변경하면 클래스로 만든 객체의 lastname 값도 모두 변경된다 = 클래스 변수는 클래스로 만든 모든 객체에 공유된다



```python
Family.lastname = "박" #Family.lastname 수정하면?
```


```python
print(a.lastname)
```

<pre>
박
</pre>

```python
print(b.lastname)
```

<pre>
박
</pre>
#### 클래스 변수와 객체 변수


- a.lastname을 변경하면?



```python
a.lastname = "최"
```


```python
print(a.lastname)
```

<pre>
최
</pre>
- 이렇게 하면 Family클래스의 lastname이 바뀌는 것이 아니라 a 객체에 lastname이라는 객체변수가 새롭게 생성

- 즉, 객체변수는 클래스 변수와 동일한 이름으로 생성 가능

- 이제부터 a.lastname은 Family클래스의 lastname이 아닌 객체 a의 객체변수 lastname을 가리킴


- a.lastname의 객체변수를 생성하더라도 Family 클래스의 lastname과는 상관이 없다



```python
print(Family.lastname)
```

<pre>
박
</pre>

```python
print(b.lastname)
```

<pre>
박
</pre>
- Family 클래스의 lastname 값은 변하지 않았다


## 5-2 모듈

- 함수나 변수 또는 클래스를 모아 놓은 파일

- 다른 파이썬 프로그램에서 불러와 사용할 수 있게끔 만든 파이썬 파일


#### 모듈 만들기

- import 모듈 이름(.py 확장자 제외)

- from 모듈 이름 import 모듈 함수


## 5-3 패키지

- 다음에 정리


## 5-4 예외 처리


### 오류는 어떨 때 발생?


- 디렉터리 안에 없는 파일을 열려고 시도



```python
f = open("나없는파일", 'r')
```

FileNotFoundError 오류 발생


- 0으로 다른 숫자를 나누는 경우



```python
4/0
```

4를 0으로 나누려니까 ZeroDivisionError 오류 발생



```python
a = [1,2,3]
```


```python
a[4]
```

IndexError 오류 발생


### 오류 예외 처리 기법


#### try, except문

- 기본 구조: <br>

  try:<br>

  ...<br>

  except [발생 오류[as 오류 메시지 변수]]:

  ...

- ***try 블록 수행 중 오류 발생*** : except 블록 수행

- ***try 블록 수행 중 오류 발생X*** : except 블록 수행되지 X


#### except 구문을 사용하는 3가지 방법


##### 1. try, except만 쓰는 방법

오류 종류에 상관없이 오류 발생하면 except 블록 수행




try: <br>

...<br>

except: <br>

...


##### 2. 발생 오류만 포함한 except문

오류 발생 시 except문에 미리 정해 놓은 오류 이름과 일치할 때만 except 블록 수행


try:<br>

...<br>

except 발생 오류:<br>

...


##### 3. 발생 오류와 오류 메시지 변수까지 포함한 except문

두 번째 경우에서 오류 메시지의 내용까지 알고 싶을 때 사용


try:<br>

...<br>

except 발생 오류 as 오류 메시지 변수:<br>

...



```python
try:
    4/0
except ZeroDivisionError as e:
    print(e)
```

<pre>
division by zero
</pre>
위처럼 4를 0으로 나누려고 하면 ZeroDivisionError가 발생해 except 블록이 실행되고 변수 e에 담기는 오류 메시지를 출력(division by zero)


- 나코딩



```python
try:
    a = [1,2,3]
    a[4]
except IndexError as e:
    print(e)
```

<pre>
list index out of range
</pre>
#### try ... finally

- finally절은 try문 수행 도중 예외 발생 여부에 상관없이 항상 수행

- 보통 finally절은 사용한 리소스를 close해야 할 때 많이 사용



```python
f = open('foo.txt', 'w')
try:
    #무언가 수행
finally:
    f.close()
```

foo.txt 파일을 쓰기 모드로 연 후 try문을 수행 후 예외 발생 여부와 상관없이 finally절에서 f.close()로 열린 파일 닫기 가능


#### 여러 개의 오류 처리하기

- 구문 : <br>

try:<br>

...<br>

except 발생 오류 1: <br>

...

except 발생 오류 2: <br>

...



```python
try:
    a = [1,2]
    print(a[3])
    4/0
except ZeroDivisionError:
    print("0으로 나눌 수 없습니다.")
except IndexError:
    print("인덱싱할 수 없습니다.")
```

<pre>
인덱싱할 수 없습니다.
</pre>
인덱싱 오류가 먼저 발생했으므로 4/0으로 발생되는 ZeroDivisionError 오류는 발생되지 않았다.


- 오류 메시지도 가져오기



```python
try:
    a = [1,2]
    print(a[3])
    4/0
except ZeroDivisionError as e:
    print(e)
except IndexError as e:
    print(e)
```

<pre>
list index out of range
</pre>
- ZeroDivisionError와 IndexError 함께 처리



```python
try:
    a = [1,2]
    print(a[3])
    4/0
except (ZeroDivisionError, IndexError) as e:
    print(e)
```

<pre>
list index out of range
</pre>
2개 이상의 오류를 동시에 처리하기 위해서는 위와 같이 괄호를 사용해 함께 묶어 처리


### 오류 회피하기



```python
try:
    f = open("나없는파일", 'r')
except FileNotFoundError: # 파일이 없더라도 오류를 발생시키지 않고 통과
    pass
```

### 오류 일부러 발생시키기(raise)

- raise 명령어를 사용해 오류를 강제로 발생시킬 수 있다.


- Bird 클래스를 상속받는 자식 클래스는 반드시 fly라는 함수를 구현하도록 만들고 싶은 경우(강제로 그렇게 하고 싶은 경우)



```python
class Bird:
    def fly(self):
        raise NotImplementedError
```

- 자식 클래스가 fly 함수를 구현하지 않은 상태로 fly 함수 호출한 경우



```python
class Eagle(Bird): #Eagle 클래스는 Bird 클래스를 상속 받음
    pass

eagle = Eagle()
eagle.fly()
```

Eagle클래스는 Bird클래스를 상속받는다. 그런데 Eagle클래스에서 fly함수를 구현하지 않았기 때문에 Bird 클래스의 fly 함수가 호출된다.<br>

그리고 raise문에 의해 NotImplemented Error 발생


- NotImplementedError가 발생되지 않도록 다음과 같이 Eagle클래스에 fly 함수 반드시 구현



```python
class Eagle(Bird):
    def fly(self):
        print("very fast")
    
eagle = Eagle()
eagle.fly()
```

<pre>
very fast
</pre>
### 예외 만들기

- 프로그램 수행 도중 특수한 경우에만 예외 처리를 하기 위해 종종 예외를 만들어서 사용

- 파이썬 내장 클래스인 Exception 클래스를 상속하여 예외를 만들 수 있다



```python
class MyError(Exception):
    pass
```

- 별명 출력해주는 함수 작성



```python
def say_nick(nick):
    if nick == '바보':
        raise MyError()
    print(nick)
```


```python
say_nick("천사")
```

<pre>
천사
</pre>

```python
say_nick("바보") # MyError 발생
```

- 예외 처리 기법을 사용해 MyError 발생을 예외 처리



```python
try:
    say_nick("천사")
    say_nick("바보")
except MyError:
    print("허용되지 않는 별명입니다.")
```

<pre>
천사
허용되지 않는 별명입니다.
</pre>
- 오류 메시지 사용한 예외 처리



```python
try:
    say_nick("천사")
    say_nick("바보")
except MyError as e:
    print(e)
```

<pre>
천사

</pre>
하지만 프로그램을 실행해 보면 print(e)로 오류 메시지가 출력되지 않음.<br>

오류 메시지 출력 시 오류 메시지가 보이게 하려면 오류 클래스에 다음과 같은 __str__ 메서드 구현<br>

__str__ 메서드 : print(e)처럼 오류 메시지를 print문으로 출력할 경우 호출되는 메서드



```python
class MyError(Exception):
    def __str__(self):
        return "허용되지 않는 별명입니다."
```


```python
try:
    say_nick("천사")
    say_nick("바보")
except MyError as e:
    print(e)
```

<pre>
천사
허용되지 않는 별명입니다.
</pre>
"허용되지 않는 별명입니다." 라는 오류메시지 출력


## 5-5 내장 함수


### abs(x)

- 어떤 숫자를 입력받았을 때, 그 숫자의 절댓값을 돌려주는 함수



```python
abs(3)
```

<pre>
3
</pre>

```python
abs(-3)
```

<pre>
3
</pre>

```python
abs(-1.2)
```

<pre>
1.2
</pre>
### all(x)

- 반복 가능한(iterable) 자료형 x를 입력 인수로 받으며 이 x가 모두 참이면 True, 거짓이 하날도 있으면 False를 돌려줌



```python
all([1,2,3])
```

<pre>
True
</pre>

```python
all([1,2,3,0])
```

<pre>
False
</pre>
### any(x)

- x 중 하나라도 참이 있으면 True를 돌려주고, x가 모두 거짓일 때에만 False를 돌려줌. all(x)의 반대



```python
any([1,2,3,0])
```

<pre>
True
</pre>

```python
any([0,""])
```

<pre>
False
</pre>
### chr(i)

- 아스키(ASCII) 코드 값을 입력받아 그 코드에 해당하는 문자를 출력하는 함수



```python
chr(97)
```

<pre>
'a'
</pre>

```python
chr(48)
```

<pre>
'0'
</pre>
### dir

- 객체가 자체적으로 가지고 있는 변수나 함수를 보여줌

- 다음 예는 리스트와 딕셔너리 객체 관련 함수(메서드)를 보여주는 예



```python
dir([1,2,3])
```

<pre>
['__add__',
 '__class__',
 '__class_getitem__',
 '__contains__',
 '__delattr__',
 '__delitem__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__gt__',
 '__hash__',
 '__iadd__',
 '__imul__',
 '__init__',
 '__init_subclass__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__mul__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__reversed__',
 '__rmul__',
 '__setattr__',
 '__setitem__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'append',
 'clear',
 'copy',
 'count',
 'extend',
 'index',
 'insert',
 'pop',
 'remove',
 'reverse',
 'sort']
</pre>

```python
dir({'1':'a'})
```

<pre>
['__class__',
 '__class_getitem__',
 '__contains__',
 '__delattr__',
 '__delitem__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__ior__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__ne__',
 '__new__',
 '__or__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__reversed__',
 '__ror__',
 '__setattr__',
 '__setitem__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'clear',
 'copy',
 'fromkeys',
 'get',
 'items',
 'keys',
 'pop',
 'popitem',
 'setdefault',
 'update',
 'values']
</pre>
### divmod(a,b)

- 2개의 숫자를 입력으로 받으며, a를 b로 나눈 몫과 나머지를 튜플 형태로 돌려줌



```python
divmod(7,3) 
```

<pre>
(2, 1)
</pre>

```python
7//3
```

<pre>
2
</pre>

```python
7%3
```

<pre>
1
</pre>
### enumerate

- '열거하다'라는 뜻. 이 함수는 순서가 있는 자료형(리스트, 튜플, 문자열)을 입력으로 받아 인덱스 값을 포함하는 enumerate 객체를 돌려줌.

- for문과 함께 자주 사용



```python
for i, name in enumerate(['body', 'foo', 'bar']):
    print(i, name)
```

<pre>
0 body
1 foo
2 bar
</pre>
### eval(expression) 

- 실행 가능한 문자열(1+2, 'hi'+'a' 같은 것)을 입력으로 받아 문자열을 실행한 결괏값을 돌려주는 함수



```python
eval('1+2')
```

<pre>
3
</pre>

```python
eval("'hi' + 'a'")
```

<pre>
'hia'
</pre>

```python
eval('divmod(4,3)')
```

<pre>
(1, 1)
</pre>
### filter

- 첫 번째 인수: 함수 이름, 두 번째 인수: 그 함수에 차례로 들어가 반복 가능한 자료형



```python
#filter함수 없이
def positive(l):
    result = []
    for i in l:
        if i > 0:
            result.append(i)
    return result

print(positive([1,-3,2,0,-5,6]))
            
```

<pre>
[1, 2, 6]
</pre>

```python
#filter 함수 사용
def positive(x):
    return x > 0

print(list(filter(positive, [1,-3,2,0,-5,6])))
```

<pre>
[1, 2, 6]
</pre>

```python
list(filter(lambda x: x>0, [1,-3,2,0,-5,6]))
```

<pre>
[1, 2, 6]
</pre>
### hex(x)

- 정수 값을 입력받아 16진수(hexadecimal)로 변환하여 돌려주는 함수



```python
hex(234)
```

<pre>
'0xea'
</pre>

```python
hex(3)
```

<pre>
'0x3'
</pre>
### id(object)

- 객체를 입력받아 객체의 고유 주소 값(레퍼런스)을 돌려주는 함수



```python
a=3
```


```python
id(3)
```

<pre>
2093048332592
</pre>

```python
b=a
```


```python
id(b)
```

<pre>
2093048332592
</pre>
- 3, a, b가 모두 같은 객체를 가리킴



```python
id(4) # 다른 고유 주소값
```

<pre>
2093048332624
</pre>
### input([prompt])

- 사용자 입력을 받는 함수



```python
a = input()
```

<pre>
 hi
</pre>

```python
a
```

<pre>
'hi'
</pre>

```python
b = input("Enter: ")
```

<pre>
Enter:  hi
</pre>

```python
b
```

<pre>
'hi'
</pre>
### int(x)

- 문자열 형태의 숫자나 소수점이 있는 숫자 등을 정수 형태로 돌려주는 함수



```python
int('3')
```

<pre>
3
</pre>

```python
int(3.4)
```

<pre>
3
</pre>
- int(x, radix)는 radix 진수로 표현된 문자열 x를 10진수로 변환하여 돌려줌



```python
int('11',2) #2진수로 표현된 11의 10진수 값 구하기
```

<pre>
3
</pre>

```python
int('1A', 16) #16진수로 표현된 1A의 10진수 값 구하기
```

<pre>
26
</pre>
### isinstance(object, class)

- 첫 번째 인수: 인스턴스 , 두 번째 인수: 클래스 이름

- 입력으로 받은 인스턴스가 그 클래스의 인스턴스인지를 판다하여 참이면 True, 거짓이면 False를 돌려줌



```python
class Person:
    pass
```


```python
a = Person()
```


```python
isinstance(a, Person) #a가 Person클래스의 인스턴스인지 확인
```

<pre>
True
</pre>

```python
b=3
```


```python
isinstance(b, Person) #b가 Person클래스의 인스턴스인지 확인
```

<pre>
False
</pre>
### len(s)

- 입력값 s의 길이(요소의 전체 개수)를 돌려주는 함수



```python
len("python")
```

<pre>
6
</pre>

```python
len([1,2,3])
```

<pre>
3
</pre>

```python
len((1,'a'))
```

<pre>
2
</pre>
### list(s)

- 반복 가능한 자료형 s를 입력받아 리스트로 만들어 돌려주는 함수



```python
list("python")
```

<pre>
['p', 'y', 't', 'h', 'o', 'n']
</pre>

```python
list((1,2,3))
```

<pre>
[1, 2, 3]
</pre>
- 리스트 함수에 리스트를 입력으로 주면 똑같은 리스트를 복사해 돌려줌



```python
a = [1,2,3]
```


```python
b = list(a)
```


```python
b
```

<pre>
[1, 2, 3]
</pre>
### map(f, iterable)

- 함수(f)와 반복 가능한(iterable) 자료형을 입력으로 받음

- map은 입력받은 자료형의 각 요소를 함수 f가 수행한 결과를 묶어서 돌려주는 함수



```python
#map 사용 전
def two_times(numberList):
    result = []
    for number in numberList:
        result.append(number*2)
    return result

result = two_times([1,2,3,4])
print(result)
```

<pre>
[2, 4, 6, 8]
</pre>

```python
#map 사용 후
def two_times(x): return x*2
```


```python
list(map(two_times, [1,2,3,4]))
```

<pre>
[2, 4, 6, 8]
</pre>

```python
list(map(lambda a:a*2, [1,2,3,4]))
```

<pre>
[2, 4, 6, 8]
</pre>
### max(iterable)

- 인수로 반복 가능한 자료형을 입력받아 그 최댓값을 돌려주는 함수



```python
max([1,2,3])
```

<pre>
3
</pre>

```python
max("python")
```

<pre>
'y'
</pre>
### min(iterable)

- max함수와 반대로, 인수로 반복 가능한 자료형을 입력받아 그 최솟값을 돌려주는 함수



```python
min([1,2,3])
```

<pre>
1
</pre>

```python
min("python")
```

<pre>
'h'
</pre>
### oct(x)

- 정수 형태의 숫자를 8진수 문자열로 바꾸어 돌려주는 함수



```python
oct(34)
```

<pre>
'0o42'
</pre>

```python
oct(12345)
```

<pre>
'0o30071'
</pre>
### open(filename, [mode])

- '파일 이름'과 '읽기 방법'을 입력받아 파일 객체를 돌려주는 함수

- 읽기 방법(mode)을 생략하면 기본값인 읽기 전용 모드(r)로 파일 객체를 만들어 돌려줌



```python
f = open("binary_file", "rb") #rb는 '바이너리 읽기 모드'
```


```python
# fread와 fread2는 동일한 방법
fread = open("read_mode.txt", 'r')
fread2 = open("read_mode.txt")
```


```python
fappend = open("append_mode.txt", 'a')
```

### ord(c)

- 문자의 아스키 코드 값을 돌려주는 함수



```python
ord('a')
```

<pre>
97
</pre>

```python
ord('0')
```

<pre>
48
</pre>
### pow

- pow(x,y)는 x의 y제곱한 결괏값을 돌려주는 함수



```python
pow(2,4)
```

<pre>
16
</pre>

```python
pow(3,3)
```

<pre>
27
</pre>
### range([start,] stop [,step])

- for문과 함께 자주 사용

- 입력받은 숫자에 해당하는 범위 값을 반복 가능한 객체로 만들어 돌려줌


#### 인수가 하나일 경우



```python
list(range(5))
```

<pre>
[0, 1, 2, 3, 4]
</pre>
#### 인수가 2개일 경우



```python
list(range(5,10))
```

<pre>
[5, 6, 7, 8, 9]
</pre>
#### 인수가 3개일 경우



```python
list(range(1,10,2))
```

<pre>
[1, 3, 5, 7, 9]
</pre>

```python
list(range(9,-10,-1))
```

<pre>
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0, -1, -2, -3, -4, -5, -6, -7, -8, -9]
</pre>
### round(number[,ndigits])

- 숫자를 입력받아 반올림해주는 함수

- round 함수의 두 번째 매개변수는 반올림하여 표시하고 싶은 소수점의 자릿수(ndigits)



```python
round(4.6)
```

<pre>
5
</pre>

```python
round(4.2)
```

<pre>
4
</pre>

```python
round(5.678,2)
```

<pre>
5.68
</pre>
### sorted(iterable)

- 입력값을 정렬한 후 그 결과를 리스트로 돌려주는 함수



```python
sorted([3,1,2])
```

<pre>
[1, 2, 3]
</pre>

```python
sorted(['a','c','b'])
```

<pre>
['a', 'b', 'c']
</pre>

```python
sorted("zero")
```

<pre>
['e', 'o', 'r', 'z']
</pre>

```python
sorted((3,2,1))
```

<pre>
[1, 2, 3]
</pre>
### str(object)

- 문자열 형태로 객체를 변환하여 돌려주는 함수



```python
str(3)
```

<pre>
'3'
</pre>

```python
str('hi')
```

<pre>
'hi'
</pre>

```python
str('hi'.upper())
```

<pre>
'HI'
</pre>
### sum(iterable)

- 입력받은 리스트나 튜플의 모든 요소의 합을 돌려주는 함수



```python
sum([1,2,3])
```

<pre>
6
</pre>

```python
sum([4,5,6])
```

<pre>
15
</pre>
### tuple

- 반복 가능한 자료형을 입력받아 튜플 형태로 바꾸어 돌려주는 함수

- 만약 튜플이 입력을 들어오면 그대로 돌려줌



```python
tuple("abc")
```

<pre>
('a', 'b', 'c')
</pre>

```python
tuple([1,2,3])
```

<pre>
(1, 2, 3)
</pre>

```python
tuple((1,2,3))
```

<pre>
(1, 2, 3)
</pre>
### type(object)

- 입력값의 자료형이 무엇인지 알려주는 함수



```python
type("abc")
```

<pre>
str
</pre>

```python
type([])
```

<pre>
list
</pre>

```python
type(open("test", 'w'))
```

<pre>
_io.TextIOWrapper
</pre>
### zip(*iterable)

- 동일한 개수로 이루어진 자료형을 묶어 주는 역할을 하는 함수

- *iterable : 반복 가능(iter-able)한 자료형 여러 개를 입력할 수 있다는 의미



```python
list(zip([1,2,3], [4,5,6]))
```

<pre>
[(1, 4), (2, 5), (3, 6)]
</pre>

```python
list(zip([1,2,3],[4,5,6],[7,8,9]))
```

<pre>
[(1, 4, 7), (2, 5, 8), (3, 6, 9)]
</pre>

```python
list(zip("abc", "def"))
```

<pre>
[('a', 'd'), ('b', 'e'), ('c', 'f')]
</pre>
## 5-6 라이브러리


# 6장 파이썬 프로그래밍, 어떻게 시작해야 할까?


## 6-1 내가 프로그램을 만들 수 있을까?


### 구구단 만들기



```python
#답1.
def GuGu(n):
    result = []
    for i in range(1,10):
        result.append(n*i)
    return result
print(GuGu(2))
```

<pre>
[2, 4, 6, 8, 10, 12, 14, 16, 18]
</pre>

```python
def GuGu(n):
    result = []
    i = 1
    while i < 10:
        result.append(n*i)
        i = i + 1
    return result
```


```python
print(GuGu(2))
```

<pre>
[2, 4, 6, 8, 10, 12, 14, 16, 18]
</pre>
### 6-2 3과 5의 배수 합하기



```python
result = 0
for n in range(1,1000):
    if n%3 == 0 or n%5 == 0:
        result += n
print(result)
```

<pre>
233168
</pre>
- 15와 같은 수를 이중으로 더하여 잘못된 결과를 출력하는 경우



```python
result = 0
for n in range(1,1000):
    if n%3 == 0:
        result += n
    if n%5 == 0:
        result += n
print(result)
```

<pre>
266333
</pre>
- 코딩연습사이트


https://euler.synap.co.kr/prob_list.php


### 6-3 게시판 페이징하기


### 게시판 프로그램 만들기 

- 게시물의 총 건수와 한 페이지에 보여 줄 게시물 수를 입력으로 주었을 때 총 페이지 수 출력



```python
def getTotalPage(m,n):
    return m // n + 1

print(getTotalPage(5,10)) # 첫 번째 케이스, 1 출력
print(getTotalPage(15,10)) # 두 번째 케이스, 2 출력
print(getTotalPage(25,10)) # 세 번째 케이스, 3 출력
print(getTotalPage(30,10)) # 네 번째 케이스, 3이 출력되어야 하는데 4가 출력
```

<pre>
1
2
3
4
</pre>
- 코드 변경



```python
def getTotalPage(m,n):
    if m % n == 0:
        return m // n
    else:
        return m // n  + 1
```


```python
print(getTotalPage(5,10)) 
print(getTotalPage(15,10)) 
print(getTotalPage(25,10)) 
print(getTotalPage(30,10))
```

<pre>
1
2
3
3
</pre>

```python
```
